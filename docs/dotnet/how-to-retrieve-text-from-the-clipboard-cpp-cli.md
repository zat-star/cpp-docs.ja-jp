---
title: "方法: クリップボードからテキストを取得 (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- text, retrieving from Clipboard
- Clipboard, retrieving text
ms.assetid: 99e77ba0-8573-4030-92d8-de8aa7623ee4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 255f2fb393ecf2c2748beada4b250b60ca965e25
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-retrieve-text-from-the-clipboard-ccli"></a>方法: クリップボードからテキストを取得する (C++/CLI)
次のコード例では、<xref:System.Windows.Forms.Clipboard.GetDataObject%2A>メンバーを返す関数へのポインター、<xref:System.Windows.Forms.IDataObject>インターフェイスです。 このインターフェイスをデータの形式のクエリを実行し、実際のデータを取得するために使用します。  
  
## <a name="example"></a>例  
  
```  
// read_clipboard.cpp  
// compile with: /clr  
#using <system.dll>  
#using <system.Drawing.dll>  
#using <system.windows.forms.dll>  
  
using namespace System;  
using namespace System::Windows::Forms;  
  
[STAThread] int main( )  
{  
   IDataObject^ data = Clipboard::GetDataObject( );  
  
   if (data)  
   {  
      if (data->GetDataPresent(DataFormats::Text))   
      {  
         String^ text = static_cast<String^>  
           (data->GetData(DataFormats::Text));  
         Console::WriteLine(text);   
      }  
      else  
         Console::WriteLine("Nontext data is in the Clipboard.");  
   }  
   else   
   {  
      Console::WriteLine("No data was found in the Clipboard.");  
   }  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>参照  
 [Windows の操作 (C + + CLI)](../dotnet/windows-operations-cpp-cli.md)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)