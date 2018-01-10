---
title: "Unicode のサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- globalization [C++], character sets
- portable data types [MFC]
- Unicode [C++]
- wide characters [C++], about wide characters
- character sets [C++], Unicode
- localization [C++], character sets
- Unicode [C++], installing support
ms.assetid: 180f1d10-8543-4f79-85ce-293d3cb443bb
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 150f161b71efc07bc7b5a08d79e17fac0dea7931
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="support-for-unicode"></a>Unicode のサポート
Unicode は、1 バイトでは表現できない文字セットを含むあらゆる文字セットをサポートする仕様です。 いずれかの Unicode を使用することをお勧め国際市場向けプログラミングしている場合または[マルチバイト文字セット](../text/support-for-multibyte-character-sets-mbcss.md)(Mbcs)、またはこれをビルドするには、スイッチを変更することでいずれかのように、プログラムを有効にします。  
  
 ワイド文字は、2 バイトの多言語文字コードです。 現代のコンピューティングにおいて世界中で使用されている文字のほとんどは、技術的な記号や特殊な出版用の文字も含め、ワイド文字としての Unicode 仕様に従って表現できます。 1 つのワイド文字では表現できない文字は、Unicode のサロゲート機能を使用して Unicode のペアで表現できます。 それぞれのワイド文字は 16 ビットの固定サイズで表現されるため、ワイド文字を使用すると、各種言語の文字セットを使うプログラミングが簡単になります。  
  
 として表されるワイド文字の文字列、 **wchar_t[]**配列およびが指す、`wchar_t*`ポインター。 ASCII 文字は、先頭に文字 L を付けることで、ワイド文字として表現できます。 たとえば、L '\0' は、終端の幅 (16 ビット) **NULL**文字です。 同様に、ASCII 文字列リテラルは、ASCII リテラルの先頭に文字 L を付けることで、ワイド文字列リテラルとして表現できます (L"Hello")。  
  
 通常、ワイド文字はマルチバイト文字よりもメモリ内の領域を多く必要としますが、処理は速くなります。 また、マルチバイト エンコードで一度に表現できるロケールは 1 つのみですが、Unicode 表現では世界中のすべての文字セットを同時に表現できます。  
  
 MFC フレームワークは Unicode に完全に対応しており、MFC では、次の表に示すように、移植性のあるマクロを使用することで Unicode 対応を実現しています。  
  
### <a name="portable-data-types-in-mfc"></a>MFC での移植性のあるデータ型  
  
|移植性のないデータ型|置き換えに使うマクロ|  
|-----------------------------|----------------------------|  
|`char`|_**TCHAR**|  
|**char\***、 **LPSTR (Win32 データ型)**|`LPTSTR`|  
|**const char\*LPCSTR (Win32 データ型)**|`LPCTSTR`|  
  
 クラス`CString`使用**_TCHAR**をベースとし、簡単な変換コンス トラクターと演算子を提供します。 Unicode の文字列操作のほとんどは、操作の基本単位が 8 ビット バイトではなく 16 ビット文字であることを除き、Windows の ANSI 文字セットの操作に使用するのと同じロジックを使用して記述できます。 マルチバイト文字セットの操作と異なり、1 つの Unicode 文字を 2 つの個別のバイトのように扱う必要はなく、また、そのような処理は適切ではありません。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [MFC による Unicode サポートをインストールします。](../mfc/unicode-in-mfc.md)  
  
-   [プログラムで Unicode を有効にします。](../text/international-enabling.md)  
  
-   [プログラムで Unicode と MBCS の両方を有効にします。](../text/internationalization-strategies.md)  
  
-   [Unicode を使用して、国際化プログラムを作成するには](../text/unicode-programming-summary.md)  
  
-   [Unicode、どの Unicode を使用して、プログラムより効率的に Windows 2000 でなどの利点を説明します](../text/benefits-of-character-set-portability.md)  
  
-   [ワイド文字の引数をプログラムに渡すためにの wmain を使用します。](../text/support-for-using-wmain.md)  
  
-   [Unicode プログラミングの概要を参照してください。](../text/unicode-programming-summary.md)  
  
-   [バイト幅の移植性に対する汎用テキスト マップの詳細します。](../text/generic-text-mappings-in-tchar-h.md)  
  
## <a name="see-also"></a>参照  
 [テキストと文字列](../text/text-and-strings-in-visual-cpp.md)   
 [wmain の使用](../text/support-for-using-wmain.md)