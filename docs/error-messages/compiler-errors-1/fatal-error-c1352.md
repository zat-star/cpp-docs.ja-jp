---
title: "致命的なエラー C1352 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1352
dev_langs:
- C++
helpviewer_keywords:
- C1352
ms.assetid: d044e8b0-b6ef-4d57-8eb5-6254071be707
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2f2a5c42eaa5afc609f1b8ee1c09875db8bff9c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1352"></a>致命的なエラー C1352
関数 'function' (元モジュール 'file') の無効な、または壊れた MSIL です。  
  
 .netmodule がコンパイラに渡されましたが、コンパイラでファイルの破損が検出されました。  調査するために .netmodule の作成者に問い合わせてください。  
  
 コンパイラは、.netmodule ファイルのすべての種類の破損をチェックしません。  ただし、return ステートメントを含む関数内のすべてのコントロール パスのすべての種類の破損をチェックします。  
  
 詳細については、「 [リンカー入力としての .netmodule ファイル](../../build/reference/netmodule-files-as-linker-input.md)」を参照してください。