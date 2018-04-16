---
title: "2.2 条件付きコンパイル |Microsoft ドキュメント"
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
ms.assetid: 8f9c914d-736c-48cf-899d-c8029dbe1e32
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1fb58458710c18f89f4057061b9c67b4eef1bbf0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="22-conditional-compilation"></a>2.2 条件付きコンパイル
_**OPENMP**マクロ名が 10 進定数として OpenMP 準拠の実装によって定義された*yyyymm*、承認済みの仕様の月と年になる予定です。 このマクロのサブジェクトをすることはできません、 **#define**または**#undef**プリプロセッサ ディレクティブです。  
  
```  
#ifdef _OPENMP  
iam = omp_get_thread_num() + index;  
#endif  
```  
  
 ベンダーは、OpenMP に拡張機能を定義する場合は、追加の定義済みマクロを指定、可能性があります。