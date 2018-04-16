---
title: "致命的なエラー C1126 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1126
dev_langs:
- C++
helpviewer_keywords:
- C1126
ms.assetid: f22b26a6-8ad7-47cf-a237-196c8ea60aca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: abe40b1813facb9531312e08371fbe769c32c119
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1126"></a>致命的なエラー C1126
'identifier': 自動メモリ割り当てサイズを超えています  
  
 関数 (swappable 関数の追加の 20 バイトなど、コンパイラで使用される領域の制限時間を加えた) のローカル変数に割り当てられた領域を超えています。  
  
 このエラーを解決するには使用`malloc`または`new`大量のデータを割り当てることです。