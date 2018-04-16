---
title: "SBCS および MBCS データ型 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MBCS
- SBCS
dev_langs:
- C++
helpviewer_keywords:
- SBCS and MBCS data types
- data types [C], MBCS and SBCS
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c54b6e9716e7f0aee9a0b211148b76804d9520bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="sbcs-and-mbcs-data-types"></a>SBCS および MBCS データ型
1 つのマルチバイト文字または 1 つのマルチバイト文字の 1 バイトを処理する Microsoft `MBCS` ランタイム ライブラリ ルーチンでは、`unsigned int` 引数が想定されます (0x00 <= 文字の値 <= 0xFFFF および 0x00 <= バイト値 <= 0xFF の場合)。 マルチバイトのバイトまたは文字列のコンテキスト内の文字を処理する `MBCS` ルーチンでは、マルチバイト文字列が `unsigned char` ポインターとして表示されることが想定されます。  
  
> [!CAUTION]
>  マルチバイト文字の各バイトは 8 ビットの `char` で表すことができます。 ただし、0x7F よりも大きい値を持つ `SBCS` または型が `char` の `MBCS` 1 バイト文字は負になります。 このような文字が直接 `int` または `long` に変換されると、結果がコンパイラによって符号拡張され、予期しない結果が生じることがあります。  
  
 そのため、マルチバイト文字のバイトを 8 ビット `unsigned char` で表すことが最善の方法となります。 また、負の結果を避けるためには、単に型 `char` の 1 バイト文字を `int` または`long` に変換する前に `unsigned char` に変換します。  
  
 `SBCS` の文字列処理関数の中には、(符号付きの) `char*` パラメーターを受け取るものがあります。このため、`_MBCS` を定義すると、型の不一致を知らせるコンパイラの警告が生成されます。 この警告を回避する方法を 3 つ、効率の順に次に示します。  
  
1.  TCHAR.H の "タイプ セーフな" インライン関数を使用します。 これが既定の動作です。  
  
2.  コマンド ラインで `_MB_MAP_DIRECT` を定義して、TCHAR.H の "直接" マクロを使用します。 この場合は、型を手作業で一致させる必要があります。 これは一番速い方法ですが、タイプ セーフではありません。  
  
3.  TCHAR.H の "タイプ セーフな" 静的リンク ライブラリ関数を使用します。 この場合は、コマンド ラインで定数 `_NO_INLINING` を定義します。 これは、一番時間がかかりますが、一番タイプ セーフな方法です。  
  
## <a name="see-also"></a>参照  
 [国際化](../c-runtime-library/internationalization.md)   
 [カテゴリ別ランタイム ルーチン](../c-runtime-library/run-time-routines-by-category.md)