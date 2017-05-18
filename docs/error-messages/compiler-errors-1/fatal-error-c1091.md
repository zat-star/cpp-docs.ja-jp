---
title: "致命的なエラー C1091 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1091
dev_langs:
- C++
helpviewer_keywords:
- C1091
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: f014e2b9d34cdac17adefe88c4947ee5fb66cfcc
ms.contentlocale: ja-jp
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1091"></a>致命的なエラー C1091
コンパイラの制限: 文字列が長さ 'length' バイトを超えています  
  
 文字列定数が文字列の長さに対する現在の制限を超えました。  
  
 2 つ (以上) の変数に静的な文字列を分割し、使用する可能性があります[strcpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)または実行時に、宣言の一部として結果を結合します。
