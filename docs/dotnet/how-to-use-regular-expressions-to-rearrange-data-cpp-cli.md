---
title: "方法: 正規表現を使用してデータを並べ替える (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- regular expressions [C++], rearranging data
- data [C++], rearranging
ms.assetid: 5f91e777-9471-424e-ba75-dca3d1b49e42
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bf60fff6c15313a6f7df1104f67c1f043f885eac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-regular-expressions-to-rearrange-data-ccli"></a>方法: 正規表現を使用してデータを再配置する (C++/CLI)
次のコード例では、.NET Framework 正規表現のサポートを使用して、再配置、またはデータの書式設定を変更する方法を示します。 次のコード例では、<xref:System.Text.RegularExpressions.Regex>と<xref:System.Text.RegularExpressions.Match>クラスを文字列からの姓と名を抽出し、逆の順序でこれらの要素の名前を表示します。  
  
 <xref:System.Text.RegularExpressions.Regex>クラスは、データの現在の形式を説明する正規表現を構築するために使用します。 2 つの名前は、コンマで区切ると見なされ、コンマの周囲の空白の任意の容量を使用できます。 <xref:System.Text.RegularExpressions.Match>各文字列を分析するメソッドを使用しています。 成功すると、姓と名から取得されます、<xref:System.Text.RegularExpressions.Match>オブジェクトを表示します。  
  
## <a name="example"></a>例  
  
```  
// regex_reorder.cpp  
// compile with: /clr  
#using <System.dll>  
using namespace System;  
using namespace Text::RegularExpressions;  
  
int main()  
{  
   array<String^>^ name =   
   {  
      "Abolrous, Sam",   
      "Berg,Matt",   
      "Berry , Jo",  
      "www.contoso.com"  
   };  
  
   Regex^ reg = gcnew Regex("(?<last>\\w*)\\s*,\\s*(?<first>\\w*)");  
  
   for ( int i=0; i < name->Length; i++ )  
   {  
      Console::Write( "{0,-20}", name[i] );  
      Match^ m = reg->Match( name[i] );  
      if ( m->Success )  
      {  
         String^ first = m->Groups["first"]->Value;  
         String^ last = m->Groups["last"]->Value;  
         Console::WriteLine("{0} {1}", first, last);  
      }  
      else  
         Console::WriteLine("(invalid)");  
   }  
   return 0;  
}  
```  
  
## <a name="see-also"></a>参照  
 [.NET Framework 正規表現](/dotnet/standard/base-types/regular-expressions)   
 [C++/CLI (Visual C++) による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)