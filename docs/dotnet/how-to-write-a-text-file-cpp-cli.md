---
title: "方法: テキスト ファイルを書き込む (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- files [C++], text
- text files, writing in C++
ms.assetid: 39ecdba6-84e0-485c-a202-84cf6d7b8d4a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 58b53159bab17ef0fddf5b26606889f89412856e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-write-a-text-file-ccli"></a>方法: テキスト ファイルを記述する (C++/CLI)
テキスト ファイルを作成し、<xref:System.IO.StreamWriter> クラスを使用してそのファイルにテキストを書き込む方法を次の例に示します。このクラスは、<xref:System.IO> 名前空間で定義されています。 <xref:System.IO.StreamWriter> コンストラクターは、作成されるファイル名を受け取ります。 ファイルが存在する場合、そのファイルに上書きされます (ただし、2 番目の <xref:System.IO.StringWriter> コンストラクター引数として True を渡す場合は例外です)。  
  
 次に、<xref:System.IO.StreamWriter.Write%2A> 関数と <xref:System.IO.TextWriter.WriteLine%2A> 関数を使用してファイルが保存されます。  
  
## <a name="example"></a>例  
  
```  
// text_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::IO;  
  
int main()   
{  
   String^ fileName = "textfile.txt";  
  
   StreamWriter^ sw = gcnew StreamWriter(fileName);  
   sw->WriteLine("A text file is born!");  
   sw->Write("You can use WriteLine");  
   sw->WriteLine("...or just Write");  
   sw->WriteLine("and do {0} output too.", "formatted");  
   sw->WriteLine("You can also send non-text objects:");  
   sw->WriteLine(DateTime::Now);  
   sw->Close();  
   Console::WriteLine("a new file ('{0}') has been written", fileName);  
  
   return 0;  
}  
```  
  
## <a name="see-also"></a>参照  
 [ファイルおよびストリーム入出力](http://msdn.microsoft.com/Library/4f4a33a9-66b7-4cd7-a285-4ad3e4276cd2)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)