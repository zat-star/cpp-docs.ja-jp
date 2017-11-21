---
title: "コンパイラ エラー C2592 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2592
dev_langs: C++
helpviewer_keywords: C2592
ms.assetid: 833a4d7b-66ef-4d4c-ae83-a533c2b0eb07
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5f6483a168ffe5f7b487932770226c834b7fd611
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2592"></a>コンパイラ エラー C2592
'class': 'base_class_2' は、'base_class_1' から継承されるので、再指定することはできません  
  
 他の基底クラスから継承していない基底クラスのみを指定できます。 この場合は、`base_class_1` が既に `base_class_2` を継承しているため、`class` の指定で必要になるのは `base_class_1` のみです。