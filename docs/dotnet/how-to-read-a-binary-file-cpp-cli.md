---
title: "方法: バイナリ ファイルの読み取り (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- files [C++], binary
- binary files, reading in C++
ms.assetid: 41ad9ad1-5cac-489c-874e-4bb3a649073a
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3714ba3df6d44559db66b56ea1a0f8a3ff7f3f44
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-read-a-binary-file-ccli"></a>方法: バイナリ ファイルを読み込む (C++/CLI)
次のコード例では、<xref:System.IO?displayProperty=fullName> の名前空間の 2 つのクラス <xref:System.IO.FileStream> と <xref:System.IO.BinaryReader> を使用して、ファイルからバイナリ データを読み取る方法を示します。 <xref:System.IO.FileStream> は実際のファイルを表し、 <xref:System.IO.BinaryReader> はバイナリへのアクセスを可能にするストリームへのインターフェイスを提供します。  
  
 このコード例は、data.bin という名前のファイルを読み取り、整数をバイナリ形式で含めます。 この種類のファイルについては、次を参照してください。[する方法: バイナリ ファイルを書き込む (C + + CLI)](../dotnet/how-to-write-a-binary-file-cpp-cli.md)です。  
  
## <a name="example"></a>例  
  
```  
// binary_read.cpp  
// compile with: /clr  
#using<system.dll>  
using namespace System;  
using namespace System::IO;  
  
int main()   
{  
   String^ fileName = "data.bin";  
   try  
   {  
      FileStream^ fs = gcnew FileStream(fileName, FileMode::Open);  
      BinaryReader^ br = gcnew BinaryReader(fs);  
  
      Console::WriteLine("contents of {0}:", fileName);  
      while (br->BaseStream->Position < br->BaseStream->Length)  
         Console::WriteLine(br->ReadInt32().ToString());  
  
      fs->Close( );  
   }  
   catch (Exception^ e)  
   {  
      if (dynamic_cast<FileNotFoundException^>(e))  
         Console::WriteLine("File '{0}' not found", fileName);  
      else  
         Console::WriteLine("Exception: ({0})", e);  
      return -1;  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>参照  
 [ファイルおよびストリーム入出力](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)