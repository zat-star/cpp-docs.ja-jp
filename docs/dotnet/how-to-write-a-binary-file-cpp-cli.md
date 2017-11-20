---
title: "方法: バイナリ ファイルを書き込む (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- binary files, writing in C++
- files [C++], binary
ms.assetid: 35d97ee6-fc7e-4c36-be18-8bbb3b44b3ae
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4aada166d8843665c645fbac90e58ef31714ab13
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-write-a-binary-file-ccli"></a>方法: バイナリ ファイルを書き込む (C++/CLI)
バイナリ データをファイルに書き込む方法を次のコード例に示します。 <xref:System.IO> 名前空間の 2 つのクラス、<xref:System.IO.FileStream> と <xref:System.IO.BinaryWriter> が使用されます。 <xref:System.IO.FileStream> は実際のファイルを表し、<xref:System.IO.BinaryWriter> はバイナリへのアクセスを可能にするストリームへのインターフェイスを提供します。  
  
 バイナリ形式の整数を含むファイルを書き込む方法を次のコード例に示します。 コードでこのファイルを読み取ることができます[する方法: バイナリ ファイルの読み取り (C + + CLI)](../dotnet/how-to-read-a-binary-file-cpp-cli.md)です。  
  
## <a name="example"></a>例  
  
```  
// binary_write.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   array<Int32>^ data = {1, 2, 3, 10000};  
  
   FileStream^ fs = gcnew FileStream("data.bin", FileMode::Create);  
   BinaryWriter^ w = gcnew BinaryWriter(fs);  
  
   try   
   {  
      Console::WriteLine("writing data to file:");  
      for (int i=0; i<data->Length; i++)  
      {  
         Console::WriteLine(data[i]);  
         w->Write(data[i]);  
      }  
   }  
   catch (Exception^)   
   {  
     Console::WriteLine("data could not be written");  
     fs->Close();  
     return -1;  
   }  
  
   fs->Close();  
   return 0;  
}  
```  
  
## <a name="see-also"></a>関連項目  
 [ファイルおよびストリーム入出力](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)