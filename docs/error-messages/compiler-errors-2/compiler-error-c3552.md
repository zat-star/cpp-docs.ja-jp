---
title: "コンパイラ エラー C3552 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3552
dev_langs:
- C++
helpviewer_keywords:
- C3552
ms.assetid: 83401524-1bf1-44c0-8aca-a6eb35c4224c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ca49c6678a147988ee0b2fb0ab57b6883b80539a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3552"></a>コンパイラ エラー C3552
'typename': 遅延指定の戻り値の型に 'auto' を含めることはできません  
  
 関数の戻り値の型のプレース ホルダーとして `auto` キーワードを使用する場合は、遅延指定の戻り値の型を指定する必要があります。 ただし、別の `auto` キーワードを使用して遅延指定の戻り値の型を指定することはできません。 たとえば、次のコード フラグメントはエラー C3552 を生成します。  
  
 `auto myFunction->auto; // C3552`