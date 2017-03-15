---
title: "Unicode のサポート | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "文字セット [C++], Unicode"
  - "グローバリゼーション [C++], 文字セット"
  - "ローカリゼーション [C++], 文字セット"
  - "移植性が高いデータ型 [MFC]"
  - "Unicode [C++]"
  - "Unicode [C++], インストールのサポート"
  - "ワイド文字 [C++], ワイド文字の概要"
ms.assetid: 180f1d10-8543-4f79-85ce-293d3cb443bb
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# Unicode のサポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unicode は、1 バイトでは表現できない文字セットを含むあらゆる文字セットをサポートする仕様です。  国際市場向けにプログラミングする場合は、Unicode か[マルチバイト文字セット](../text/support-for-multibyte-character-sets-mbcss.md) \(MBCS\) のいずれかを使用するか、またはスイッチを変更することでプログラムをそのいずれかでビルドできるようにすることをお勧めします。  
  
 ワイド文字は、2 バイトの多言語文字コードです。  現代のコンピューティングにおいて世界中で使用されている文字のほとんどは、技術的な記号や特殊な出版用の文字も含め、ワイド文字としての Unicode 仕様に従って表現できます。  1 つのワイド文字では表現できない文字は、Unicode のサロゲート機能を使用して Unicode のペアで表現できます。  それぞれのワイド文字は 16 ビットの固定サイズで表現されるため、ワイド文字を使用すると、各種言語の文字セットを使うプログラミングが簡単になります。  
  
 ワイド文字列は **wchar\_t\[\]** 配列として表現され、`wchar_t*` ポインターで指し示されます。  ASCII 文字は、先頭に文字 L を付けることで、ワイド文字として表現できます。  たとえば、L'\\0' はワイド文字 \(16 ビット\) の終端の **NULL** 文字です。  同様に、ASCII 文字列リテラルは、ASCII リテラルの先頭に文字 L を付けることで、ワイド文字列リテラルとして表現できます \(L"Hello"\)。  
  
 通常、ワイド文字はマルチバイト文字よりもメモリ内の領域を多く必要としますが、処理は速くなります。  また、マルチバイト エンコードで一度に表現できるロケールは 1 つのみですが、Unicode 表現では世界中のすべての文字セットを同時に表現できます。  
  
 MFC フレームワークは Unicode に完全に対応しており、MFC では、次の表に示すように、移植性のあるマクロを使用することで Unicode 対応を実現しています。  
  
### MFC での移植性のあるデータ型  
  
|移植性のないデータ型|置き換えに使うマクロ|  
|----------------|----------------|  
|`char`|\_**TCHAR**|  
|**char\***、**LPSTR \(Win32 データ型\)**|`LPTSTR`|  
|**const char\*、LPCSTR \(Win32 データ型\)**|`LPCTSTR`|  
  
 クラス `CString` では **\_TCHAR** が基本として使用され、変換を簡単にするためにコンストラクターと演算子が提供されます。  Unicode の文字列操作のほとんどは、操作の基本単位が 8 ビット バイトではなく 16 ビット文字であることを除き、Windows の ANSI 文字セットの操作に使用するのと同じロジックを使用して記述できます。  マルチバイト文字セットの操作と異なり、1 つの Unicode 文字を 2 つの個別のバイトのように扱う必要はなく、また、そのような処理は適切ではありません。  
  
## 目的に合ったトピックをクリックしてください  
  
-   [MFC による Unicode サポートのインストール](../mfc/unicode-in-mfc.md)  
  
-   [Unicode 対応について](../text/international-enabling.md)  
  
-   [国際化のアプローチ](../text/internationalization-strategies.md)  
  
-   [Unicode を使用した国際化されたプログラムの作成](../text/unicode-programming-summary.md)  
  
-   [Unicode の利点について \(Windows 2000 で Unicode を使用してプログラムを効率化する方法を含む\)](../text/benefits-of-character-set-portability.md)  
  
-   [ワイド文字引数をプログラムに渡すための wmain の使用](../text/support-for-using-wmain.md)  
  
-   [Unicode のプログラミングの概要の確認](../text/unicode-programming-summary.md)  
  
-   [Tchar.h における汎用テキストのマッピング](../Topic/Generic-Text%20Mappings%20in%20Tchar.h.md)  
  
## 参照  
 [テキストと文字列](../text/text-and-strings-in-visual-cpp.md)   
 [wmain の使用](../text/support-for-using-wmain.md)