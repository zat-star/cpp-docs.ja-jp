---
title: "方法: クリップボード内にテキストを格納する (C++/CLI) | Microsoft Docs"
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
  - "クリップボードのトピック, 格納 (テキストを)"
  - "テキスト, 格納 (クリップボードに)"
ms.assetid: 9996023f-b700-47ad-8ad9-1ba201eaa5a6
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: クリップボード内にテキストを格納する (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

<xref:System.Windows.Forms> 名前空間で定義される <xref:System.Windows.Forms.Clipboard> オブジェクトを使用して、文字列を格納する方法を次のコード例に示します。  このオブジェクトには、<xref:System.Windows.Forms.Clipboard.SetDataObject%2A> と <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> の 2 つのメンバー関数が用意されています。  <xref:System.Object> から派生した任意のオブジェクトを <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> に送信することで、クリップボードにデータが格納されます。  
  
## 使用例  
  
```  
// store_clipboard.cpp  
// compile with: /clr  
#using <System.dll>  
#using <System.Drawing.dll>  
#using <System.Windows.Forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
  
[STAThread] int main()  
{  
   String^ str = "This text is copied into the Clipboard.";  
  
   // Use 'true' as the second argument if  
   // the data is to remain in the clipboard  
   // after the program terminates.  
   Clipboard::SetDataObject(str, true);  
  
   Console::WriteLine("Added text to the Clipboard.");  
  
   return 0;  
}  
```  
  
## 参照  
 [方法: クリップボードからテキストを取得する](../Topic/How%20to:%20Retrieve%20Text%20from%20the%20Clipboard%20\(C++-CLI\).md)   
 [Windows の操作](../dotnet/windows-operations-cpp-cli.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)