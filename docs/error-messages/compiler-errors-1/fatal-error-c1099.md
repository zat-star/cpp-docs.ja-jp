---
title: "致命的なエラー C1099 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1099
dev_langs:
- C++
helpviewer_keywords:
- C1099
ms.assetid: c050b074-a06a-4026-9e10-569029cc0739
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 74ef24f35084e76d6f8ad9d3eec3459e7f50a930
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1099"></a>致命的なエラー C1099
エディット コンティニュ エンジンはコンパイルを終了しています。  
  
 エディット コンティニュはコード変更をコンパイルする準備としてプリコンパイル済みヘッダー ファイルを読み込みましたが、その後のアクション (プリコンパイル済みヘッダーの `#include` ステートメントの前のコード変更、またはデバッガーの停止など) により、エディット コンティニュはこのプロセスでコンパイルを完了できませんでした。 このエラーを解決するために操作を実行する必要はありません。
