---
title: "致命的なエラー C1047 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1047
dev_langs: C++
helpviewer_keywords: C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6ddc117d1e83c635bfbc644606c6c8c6032ff4f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1047"></a>致命的なエラー C1047
オブジェクトまたはライブラリ ファイル 'file' は、他のオブジェクトよりも古いコンパイラで作成されました。古いオブジェクトおよびライブラリをリビルドしてください  
  
 C1047 は、 **/LTCG** を指定してビルドされたオブジェクト ファイルまたはライブラリがリンクされるときに、それらのオブジェクト ファイルまたはライブラリが、異なるバージョンの Visual C++ ツールセットでビルドされている場合に発生します。  
  
 これは、新しいバージョンのコンパイラの使用を開始するときに、既存のオブジェクト ファイルまたはライブラリをクリーンにリビルドしない場合に発生することがあります。  
  
 C1047 を解決するには、オブジェクト ファイルまたはライブラリをすべてリビルドします。