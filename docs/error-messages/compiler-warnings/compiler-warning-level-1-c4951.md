---
title: "コンパイラの警告 (レベル 1) C4951 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4951
dev_langs:
- C++
helpviewer_keywords:
- C4951
ms.assetid: 669d8bb7-5efa-4ba9-99db-4e65addbf054
caps.latest.revision: 8
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 8317491a1649741c3322af3125fef80c0fb52f47
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4951"></a>コンパイラの警告 (レベル 1) C4951
プロファイル データ が収集されてから、'function' が編集されました。関数のプロファイル データは使用されません。  
  
 入力モジュールの関数が編集された[/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)、プロファイル データが現在無効にされるようにします。 入力モジュールは、 **/LTCG:PGINSTRUMENT** の後に再コンパイルされ、***/LTCG:PGINSTRUMENT***の操作時にモジュールに含まれていたものとは異なる制御フローを使用した関数 ( **function** ) が含まれています。  
  
 これは、情報提供の警告です。 この警告を解決するには、 **/LTCG:PGINSTRUMENT**を実行してすべてのテストを再実行し、 **/LTCG:PGOPTIMIZE**を実行します。  
  
 **/LTCG:PGOPTIMIZE** が使用されていた場合、この警告はエラーに置き換わることがあります。
