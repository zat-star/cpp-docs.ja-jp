---
title: "方法: リフレクションを使用してプラグイン コンポーネント アーキテクチャを実装する (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "プラグイン [C++]"
  - "リフレクション [C++], プラグイン"
ms.assetid: 4f31e42b-78d1-48b9-8fdc-f28c75e8e77e
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: リフレクションを使用してプラグイン コンポーネント アーキテクチャを実装する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

単純な "プラグイン" アーキテクチャを実装するためにリフレクションを使用する方法を次のコード例に示します。  最初のコード例はアプリケーションで、次のコード例はプラグインです。  アプリケーションは、コマンド ライン引数として指定されたプラグイン DLL 内の任意のフォーム ベースのクラスを使用して、アプリケーション自体を表示するマルチ ドキュメント フォームです。  
  
 アプリケーションは、<xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> メソッドを使用して、指定されたアセンブリの読み込みを試みます。  正常に処理できた場合、<xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> メソッドを使用して、アセンブリ内部の型を列挙します。  次に、<xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> メソッドを使用して、各型の互換性を確認します。  この例では、指定されたアセンブリ内で検出したクラスを、<xref:System.Windows.Forms.Form> クラスから派生させ、プラグインとして分類する必要があります。  
  
 その後、<xref:System.Activator.CreateInstance%2A?displayProperty=fullName> メソッドを使用して、互換性のあるクラスのインスタンスを生成します。このメソッドは、引数として <xref:System.Type> を受け入れ、新しいインスタンスにポインターを返します。  次に、新しい各インスタンスをフォームにアタッチし、表示します。  
  
 ただし、<xref:System.Reflection.Assembly.Load%2A> メソッドは、ファイル拡張子を含むアセンブリ名を受け入れません。  アプリケーションの main 関数は、指定された拡張子をトリムします。したがって、次のコード例はいずれの場合も動作します。  
  
## 使用例  
 次のコードは、プラグインを受け入れるアプリケーションを定義します。  アセンブリ名は、最初の引数として指定する必要があります。  このアセンブリには、少なくとも 1 つのパブリックな <xref:System.Windows.Forms.Form> 派生型を含める必要があります。  
  
```  
// plugin_application.cpp  
// compile with: /clr /c  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
  
ref class PluggableForm : public Form  {  
public:  
   PluggableForm() {}  
   PluggableForm(Assembly^ plugAssembly) {  
      Text = "plug-in example";  
      Size = Drawing::Size(400, 400);  
      IsMdiContainer = true;  
  
      array<Type^>^ types = plugAssembly->GetTypes( );  
      Type^ formType = Form::typeid;  
  
      for (int i = 0 ; i < types->Length ; i++) {  
         if (formType->IsAssignableFrom(types[i])) {  
            // Create an instance given the type description.  
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));  
            if (f) {  
               f->Text = types[i]->ToString();  
               f->MdiParent = this;  
               f->Show();  
            }  
         }  
      }  
   }  
};  
  
int main() {  
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");  
   Application::Run(gcnew PluggableForm(a));  
}  
```  
  
## 使用例  
 次のコードは、<xref:System.Windows.Forms.Form> から派生したクラスを 3 つ定義します。  結果のアセンブリ名の名前が上の一覧の実行可能ファイルに渡されると、コンパイル時にこれらのクラスはすべてホスト アプリケーションから不明であったにもかかわらず、3 つすべてのクラスが検出され、インスタンス化されます。  
  
```  
// plugin_assembly.cpp  
// compile with: /clr /LD  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
using namespace System::Reflection;  
using namespace System::Drawing;  
  
public ref class BlueForm : public Form {  
public:  
   BlueForm() {  
      BackColor = Color::Blue;  
   }  
};  
  
public ref class CircleForm : public Form {  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);  
   }  
};  
  
public ref class StarburstForm : public Form {  
public:  
   StarburstForm(){  
      BackColor = Color::Black;  
   }  
protected:  
   virtual void OnPaint(PaintEventArgs^ args) override {  
      Pen^ p = gcnew Pen(Color::Red, 2);  
      Random^ r = gcnew Random( );  
      Int32 w = ClientSize.Width;  
      Int32 h = ClientSize.Height;  
      for (int i=0; i<100; i++) {  
         float x1 = w / 2;  
         float y1 = h / 2;  
         float x2 = r->Next(w);  
         float y2 = r->Next(h);  
         args->Graphics->DrawLine(p, x1, y1, x2, y2);  
      }  
   }  
};  
```  
  
## 参照  
 [リフレクション](../dotnet/reflection-cpp-cli.md)