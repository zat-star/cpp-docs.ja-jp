---
title: "関数宣言内でのストレージ クラス指定子の使用 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- function specifiers, storage class
- declaring functions, specifiers
- external declarations
- specifiers, function
- external linkage, function declarations
- external linkage, storage-class specifiers
ms.assetid: 801d7df2-efa9-4924-a725-274a5654cfd4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f7d8b6ba1c0287492195ee891b1a573bf74de6cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="storage-class-specifiers-with-function-declarations"></a>関数宣言内でのストレージ クラス指定子の使用
関数宣言では、**static** または `extern` のストレージ クラス指定子のいずれかを使用できます。 関数には常にグローバル有効期間があります。  
  
 **Microsoft 固有の仕様**  
  
 内部レベルでの関数宣言は、外部レベルでの関数宣言と同じ意味になります。 これは、関数がローカル スコープで宣言されていても、その宣言位置から翻訳単位の残り全体で可視になることを意味しています。  
  
 **Microsoft 固有の仕様はここまで**  
  
 関数の表示規則は、次のように、変数の規則とは若干異なります。  
  
-   **static** として宣言された関数は、定義されているソース ファイル内でのみ表示されます。 同じソース ファイル内の関数は **static** 関数を呼び出すことができますが、他のソース ファイルの関数は名前で static 関数に直接アクセスすることはできません。 異なるソース ファイルにある同じ名前の別の **static** 関数は、競合することなく宣言できます。  
  
-   `extern` として宣言された関数は、(後で **static** のような関数を再宣言しない場合) プログラムのすべてのソース ファイルで参照されます。 どの関数も `extern` 関数を呼び出すことができます。  
  
-   ストレージ クラスの指定子を省略する関数宣言は既定で `extern` です。  
  
 **Microsoft 固有の仕様**  
  
 Microsoft では、**静的**として `extern` ID を再定義できます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [C ストレージ クラス](../c-language/c-storage-classes.md)