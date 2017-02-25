---
title: "コンパイラの警告 (レベル 1) C4462 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4462"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4462"
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
caps.latest.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 4
---
# コンパイラの警告 (レベル 1) C4462
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

型の GUID を特定できません。プログラムは、実行時に失敗する可能性があります。  
  
 C4462 警告は、パブリックな `TypedEventHandler` に、型パラメーターの 1 つとして外側のクラスへの参照が含まれる場合に、Windows ランタイム アプリケーションまたはコンポーネントで発生します。  
  
 **この警告が発生するコードの種類を次に示します。**  
  
```  
namespace N  
{  
       public ref struct EventArgs sealed {};  
       public ref struct R sealed  
       {  
              R() {}  
              event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;  
       };  
}  
  
[Platform::MTAThread]  
int main()  
{  
     auto x = ref new N::R();  
}  
  
```  
  
 **エラーを解決するには:**  
  
 このエラーを回避する方法は 2 つあります。  1 つは、次の例に示すように、イベント内部のアクセシビリティを、同じ実行可能ファイル内のコードで使用できるように提供する方法です。このアクセシビリティは、他の Windows ランタイム コンポーネントのコードでは使用できないようにします。  
  
```  
  
internal:  
event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;  
  
```  
  
 イベントがパブリックであることが求められる場合は、もう 1 つの方法で回避できます。この方法は既定のインターフェイスによって公開されます。  
  
```  
  
ref struct R;  
public interface struct IR { event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e; };  
  
public ref struct R sealed : [Windows::Foundation::Metadata::Default] IR  
{  
    R() {}  
    virtual event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;  
};  
  
```  
  
 `Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^` 型の GUID が使用されるのは、他のコンポーネントからその型にアクセスする場合だけです。  最初の方法は、問題回避の後、独自のコンポーネント内でのみアクセスできるため機能します。  それ以外の場合、コンパイラは最悪の場合を想定する必要があり、警告を出力します。