---
title: "致命的なエラー C1352 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1352
dev_langs:
- C++
helpviewer_keywords:
- C1352
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
caps.latest.revision: 7
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
ms.openlocfilehash: 66584dc786a3340deeaf1176362bf64dafacd3b8
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1352"></a>致命的なエラー C1352
関数 'function' (元モジュール 'file') の無効な、または壊れた MSIL です。  
  
 .netmodule がコンパイラに渡されましたが、コンパイラでファイルの破損が検出されました。  調査するために .netmodule の作成者に問い合わせてください。  
  
 コンパイラは、.netmodule ファイルのすべての種類の破損をチェックしません。  ただし、return ステートメントを含む関数内のすべてのコントロール パスのすべての種類の破損をチェックします。  
  
 詳細については、次を参照してください。[リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)です。
