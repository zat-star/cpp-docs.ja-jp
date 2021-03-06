---
title: "国際対応戦略 |Microsoft ドキュメント"
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
- globalization [C++], character sets
- language-portable code [C++]
- MBCS [C++], internationalization strategies
- Windows API [C++], international programming strategies
- Win32 [C++], international programming strategies
- Unicode [C++], globalizing applications
- character sets [C++], international programming strategies
- localization [C++], character sets
ms.assetid: b09d9854-0709-4b9a-a00c-b0b8bc4199b1
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ead6470bbbeacd43326f4373877eb991e5899116
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2018
---
# <a name="internationalization-strategies"></a>国際化のアプローチ
ターゲット オペレーティング システムと市場、に応じていくつかの国際対応戦略がある場合。  
  
-   アプリケーションで Unicode を使用します。  
  
     Unicode 固有の機能を使用して、(プログラムの一部の ANSI 文字を使用するには特別な目的で) には、すべての文字が 16 ビット幅。 C ランタイム ライブラリは、Unicode 専用のプログラミングの関数、マクロ、およびデータ型を提供します。 MFC は、完全に Unicode に対応します。  
  
-   アプリケーションでは、MBCS を使用し、任意の Win32 プラットフォームで実行できます。  
  
     MBCS 固有の機能を使用するとします。 文字列には、1 バイト文字、2 バイト文字、またはその両方を含めることができます。 C ランタイム ライブラリは、MBCS 専用のプログラミングの関数、マクロ、およびデータ型を提供します。 MFC は、MBCS に対応しています。  
  
-   移植性を高めるのため、アプリケーションのソース コードが記述された — シンボルの再コンパイルして**_UNICODE**または記号**_MBCS**定義されている、いずれかを使用するバージョンを生成できます。 詳細については、次を参照してください。 [Tchar.h における汎用テキスト マッピング](../text/generic-text-mappings-in-tchar-h.md)です。  
  
     完全に移植できる C ランタイム関数、マクロ、およびデータ型を使用するとします。 MFC の柔軟性は、これらの方法のいずれかをサポートします。  
  
 これらのトピックの残りの部分は、Unicode と MBCS をビルドすると完全に移植可能なコードの作成に集中できます。  
  
## <a name="see-also"></a>参照  
 [Unicode と MBCS](../text/unicode-and-mbcs.md)   
 [ロケールとコード ページ](../text/locales-and-code-pages.md)