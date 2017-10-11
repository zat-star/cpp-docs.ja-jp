---
title: "致命的なエラー C1852 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1852
dev_langs:
- C++
helpviewer_keywords:
- C1852
ms.assetid: fa011004-b8d6-46f1-ba80-4785e4ce137f
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cd7168c6ffa653af54404bf81cdc4d308a76783a
ms.contentlocale: ja-jp
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1852"></a>致命的なエラー C1852
'filename' は有効なプリコンパイル済みヘッダー ファイルではありません  
  
 ファイルはプリコンパイル済みヘッダーではありません。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  **/Yu** または **#pragma hdrstop**で指定された無効なファイル。  
  
2.  特に指定がない場合、コンパイラはファイル拡張子を .pch と想定します。
