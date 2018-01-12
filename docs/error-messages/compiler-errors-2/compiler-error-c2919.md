---
title: "コンパイラ エラー C2919 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2919
dev_langs: C++
helpviewer_keywords: C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e2bde12c4c6ffa94f55e9dd205c3132a755ad94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2919"></a>コンパイラ エラー C2919
'type': WinRT 型の発行サーフェスでは演算子は使用できません  
  
 Windows ランタイムの型システムでは、型の発行サーフェスで演算子メンバー関数をサポートしていません。 これは、すべての言語で演算子メンバー関数を使用できるとは限らないためです。 同じクラスまたはコンパイル ユニット内に、C++ コードから呼び出されるプライベートまたは内部の演算子メンバー関数を作成できます。  
  
 この問題を解決するには、演算子メンバー関数をパブリック インターフェイスから削除するか、名前付きのメンバー関数に変更します。 たとえば、`operator==` の代わりに、メンバー関数に `Equals` という名前を付けます。