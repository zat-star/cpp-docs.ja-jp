---
title: "リソース コンパイラの警告 RC4093 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC4093
dev_langs:
- C++
helpviewer_keywords:
- RC4093
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d21cbba379e72675b8957be58dc712b83673947
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-warning-rc4093"></a>リソース コンパイラの警告 RC4093
文字定数の非アクティブなコードでエスケープされていない改行  
  
 定数式、 `#if`、 `#elif`、 **#ifdef**、または**#ifndef**プリプロセッサ ディレクティブが 0 の場合、コードを作成するために評価が非アクティブに従います。 その使用頻度の低いコード内では、改行文字は、一重引用符または二重引用符のセット内で表示されます。  
  
 [次へ] のダブル クォーテーション マークまでのすべてのテキストは、文字定数内にあると見なされます。