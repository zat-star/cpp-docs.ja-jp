---
title: "NMAKE の致命的なエラー U1059 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U1059
dev_langs:
- C++
helpviewer_keywords:
- U1059
ms.assetid: b21d9198-9c63-40d0-b589-80e17294ce24
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fb9ba98b0f82c158e4e11859e85af72efdbbc244
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1059"></a>NMAKE の致命的なエラー U1059
構文エラー: '}' に依存するがありません  
  
 依存ファイルの検索パスが正しく指定されていません。 パスまたは右中かっこで空白が存在していた (**}**) は省略されました。  
  
 ディレクトリの仕様を相互に依存するための構文します。  
  
 **{**   
 ***ディレクトリ*} 依存**  
  
 ここで`directories`1 つまたは複数のパス、それぞれをセミコロンで区切って指定 (**;**)。 スペースは許可されません。  
  
 マクロで検索パスの一部または全体が置き換えられた場合、マクロ展開でスペースが存在しないことを確認します。