---
title: "コンパイラ エラー C2129 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2129
dev_langs: C++
helpviewer_keywords: C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e2c5bd1b79960f83ef6effeb064375d6b49e8f20
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2129"></a>コンパイラ エラー C2129
静的関数 'function' が宣言されていますが、定義されていません  
  
 前方参照される、`static`定義されていない関数です。  
  
 A`static`ファイル スコープ内で関数を定義する必要があります。 宣言する必要があります、関数が別のファイルで定義されている場合`extern`です。