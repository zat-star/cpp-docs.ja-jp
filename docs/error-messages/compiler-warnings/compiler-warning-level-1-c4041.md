---
title: "コンパイラの警告 (レベル 1) C4041 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4041
dev_langs:
- C++
helpviewer_keywords:
- C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 42779d33cad8fc867b08b412d2ded294360a0812
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4041"></a>コンパイラの警告 (レベル 1) C4041
コンパイラの制限 : ブラウザーの出力を中止します。  
  
 ブラウザー情報がコンパイラの制限を超えました。  
  
 この警告は、 [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) (ローカル変数を含めたブラウザー情報) でコンパイルすると発生することがあります。  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>修復の可能性がある解決策  
  
1.  /Fr (ローカル変数を含まないブラウザー情報) でコンパイルします。  
  
2.  ブラウザーの出力 (/FR や /Fr なしのコンパイル) を無効にします。