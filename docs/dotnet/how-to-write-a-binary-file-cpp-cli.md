---
title: "方法: バイナリ ファイルを書き込む (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "バイナリ ファイル, 書き込み (C++ での)"
  - "ファイル [C++], バイナリ"
ms.assetid: 35d97ee6-fc7e-4c36-be18-8bbb3b44b3ae
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: バイナリ ファイルを書き込む (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

バイナリ データをファイルに書き込む方法を次のコード例に示します。  <xref:System.IO> 名前空間の 2 つのクラス、<xref:System.IO.FileStream> と <xref:System.IO.BinaryWriter> が使用されます。  <xref:System.IO.FileStream> は実際のファイルを表し、<xref:System.IO.BinaryWriter> はバイナリへのアクセスを可能にするストリームへのインターフェイスを提供します。  
  
 バイナリ形式の整数を含むファイルを書き込む方法を次のコード例に示します。  このファイルは、「[方法: バイナリ ファイルを読み込む](../Topic/How%20to:%20Read%20a%20Binary%20File%20\(C++-CLI\).md)」に示されているコードを使用して読み込むことができます。  
  
## 使用例  
  
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
  
## 参照  
 [ファイルおよびストリーム入出力](../Topic/File%20and%20Stream%20I-O.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)