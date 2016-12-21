---
title: "方法: グローバル例外ハンドラーを定義およびインストールする | Microsoft Docs"
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
  - "ハンドラー, global"
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: グローバル例外ハンドラーを定義およびインストールする
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のコード例はハンドルされない例外キャプチャされたがどのようになるかを示します。  例のフォームが押されたときに null 参照を実行する例外をスローしますボタンが含まれています。  この機能は、一般的なコード エラーを表します。  発生した例外は、Main 関数によってインストールされるアプリケーション全体の例外ハンドラーによってキャッチされます。  
  
 これは <xref:System.Windows.Forms.Application.ThreadException> イベントにデリゲートをバインドすることによって実現されます。  この場合、後続の例外は `App::OnUnhandled` のメソッドに送信されます。  
  
## 使用例  
  
```  
// global_exception_handler.cpp  
// compile with: /clr  
#using <system.dll>  
#using <system.drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Threading;  
using namespace System::Drawing;  
using namespace System::Windows::Forms;  
  
ref class MyForm : public Form  
{  
   Button^ b;  
public:  
   MyForm( )  
   {  
      b = gcnew Button( );  
      b->Text = "Do Null Access";  
      b->Size = Drawing::Size(150, 30);  
      b->Click += gcnew EventHandler(this, &MyForm::OnClick);  
      Controls->Add(b);  
   }  
   void OnClick(Object^ sender, EventArgs^ args)   
   {  
      // do something illegal, like call through a null pointer...  
      Object^ o = nullptr;  
      o->ToString( );        
   }  
};  
  
ref class App  
{  
public:  
   static void OnUnhandled(Object^ sender, ThreadExceptionEventArgs^ e)  
   {  
      MessageBox::Show(e->Exception->Message, "Global Exeception");  
      Application::ExitThread( );  
   }  
};  
  
int main()  
{  
   Application::ThreadException += gcnew   
      ThreadExceptionEventHandler(App::OnUnhandled);  
  
   MyForm^ form = gcnew MyForm( );  
   Application::Run(form);  
}  
```  
  
## 参照  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)