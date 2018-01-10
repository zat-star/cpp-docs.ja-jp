---
title: "致命的なエラー C1099 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1099
dev_langs: C++
helpviewer_keywords: C1099
ms.assetid: c050b074-a06a-4026-9e10-569029cc0739
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 928ced6fe9e283cf16db651ecbf6164164e3174e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1099"></a>致命的なエラー C1099
エディット コンティニュ エンジンはコンパイルを終了しています。  
  
 エディット コンティニュはコード変更をコンパイルする準備としてプリコンパイル済みヘッダー ファイルを読み込みましたが、その後のアクション (プリコンパイル済みヘッダーの `#include` ステートメントの前のコード変更、またはデバッガーの停止など) により、エディット コンティニュはこのプロセスでコンパイルを完了できませんでした。 このエラーを解決するために操作を実行する必要はありません。