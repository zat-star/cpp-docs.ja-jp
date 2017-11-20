---
title: "NMAKE の致命的なエラー U1035 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: U1035
dev_langs: C++
helpviewer_keywords: U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a4d672618656b72ab7ac4c4ed617c90080b58304
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE の致命的なエラー U1035
構文エラー: 予想 ':' または '=' 区切り記号  
  
 いずれか、コロン (**:**) または等号 (=) (**=**) が必要です。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  ターゲットの後ろにコロンがありません。  
  
2.  1 文字のターゲットの後にコロンと (a:) などの領域がありません。 (Nmake の) には、ドライブの指定とそれが解釈されます。  
  
3.  推論規則の後ろにコロンがありません。  
  
4.  マクロ定義は、等号 (=) で後にありません。  
  
5.  後ろに円記号の文字 (**\\**) が新しい行にコマンドを続行することが使用されました。  
  
6.  NMAKE の構文規則に従っていない文字列が表示されます。  
  
7.  メイクファイルのワード プロセッサで形式でした。