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
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 4f5346a3adb5535242207ebc3a3c9b2fcffa7a40
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1126"></a>致命的なエラー C1126
'identifier': 自動メモリ割り当てサイズを超えています  
  
 関数 (swappable 関数の追加の 20 バイトなど、コンパイラで使用される領域の制限時間を加えた) のローカル変数に割り当てられた領域を超えています。  
  
 このエラーを解決するには使用`malloc`または`new`大量のデータを割り当てることです。
