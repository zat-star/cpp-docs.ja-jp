---
title: "方法: テキスト ファイルを読み込む (C++/CLI) | Microsoft Docs"
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
  - "読み取り (テキスト ファイルを)"
  - "テキスト ファイル, 読み取り"
ms.assetid: 80551c01-d769-4b6d-8db7-fd53bde21b62
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: テキスト ファイルを読み込む (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

<xref:System.IO.StreamReader> クラスを使用して、テキスト ファイルを一度に 1 行ずつ開いて読み取る方法を次の例に示します。このクラスは、<xref:System.IO?displayProperty=fullName> 名前空間で定義されています。  このクラスのインスタンスを使用してテキスト ファイルを開いてから、<xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName> メソッドを使用して各行を取得します。  
  
 このコード例では、テキストが含まれる textfile.txt というファイルを読み取ります。  この種類のファイルの詳細については、「[方法: テキスト ファイルを記述する](../Topic/How%20to:%20Write%20a%20Text%20File%20\(C++-CLI\).md)」を参照してください。  
  
## 使用例  
  
```  
// text_read.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()  
{  
   String^ fileName = "textfile.txt";  
   try   
   {  
      Console::WriteLine("trying to open file {0}...", fileName);  
      StreamReader^ din = File::OpenText(fileName);  
  
      String^ str;  
      int count = 0;  
      while ((str = din->ReadLine()) != nullptr)   
      {  
         count++;  
         Console::WriteLine("line {0}: {1}", count, str );  
      }  
   }  
   catch (Exception^ e)  
   {  
      if (dynamic_cast<FileNotFoundException^>(e))  
         Console::WriteLine("file '{0}' not found", fileName);  
      else  
         Console::WriteLine("problem reading file '{0}'", fileName);  
   }  
  
   return 0;  
}  
```  
  
## 参照  
 [ファイルおよびストリーム入出力](../Topic/File%20and%20Stream%20I-O.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)