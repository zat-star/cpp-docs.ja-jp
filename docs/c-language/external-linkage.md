---
title: "外部リンケージ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: aef61c580306cc40ef1a89c6a389c7fbaf64a5f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="external-linkage"></a>外部リンケージ
ID のファイル スコープ レベルの最初の宣言で **static** ストレージ クラス指定子を使用していない場合、オブジェクトに外部リンケージがあります。  
  
 関数の ID の宣言に *storage-class-specifier* がない場合、そのリンケージは、*storage-class-specifier* `extern` で宣言されている場合とまったく同じように決定されます。 オブジェクトの ID の宣言にファイル スコープがあり、*storage-class-specifier* が含まれていない場合、リンケージは外部になります。  
  
 外部リンケージを持つ識別子の名前は、外部リンケージを持つ同じ名前の他の宣言で指定されるものと同じ関数またはデータ オブジェクトを指定します。 2 つの宣言を同じ翻訳単位または異なる翻訳単位に配置できます。 オブジェクトまたは関数にグローバル有効期間もある場合、オブジェクトまたは関数はプログラム全体で共有されます。  
  
## <a name="see-also"></a>参照  
 [extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)