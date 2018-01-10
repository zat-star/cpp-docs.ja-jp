---
title: "プロファイル ガイド付き最適化のエラー PG0165 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: PG0165
dev_langs: C++
helpviewer_keywords: PG0165
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32b9f5f3ee335aac0a8382377aa850c3b91a27a0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="profile-guided-optimization-error-pg0165"></a>ガイド付き最適化のプロファイルのエラー PG0165
'Filename.pgd' を読み込んでいます: ' PGD バージョンがサポートされていません (バージョンの不一致)' です。  
  
 PGD ファイルは、特定のコンパイラ ツールセットを特定します。 別のコンパイラを使用するものを使用しているときにこのエラーは生成*Filename*.pgd です。 このエラーは、このコンパイラ ツールセットがからデータを使用できないことを示して*Filename*.pgd を現在のプログラムを最適化します。  
  
 この問題を解決するには、再生成*Filename*.pgd 現在コンパイラ ツールセットを使用しています。