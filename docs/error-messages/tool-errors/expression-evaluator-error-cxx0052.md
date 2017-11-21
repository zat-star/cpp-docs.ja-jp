---
title: "式エバリュエーター エラー CXX0052 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0052
dev_langs: C++
helpviewer_keywords:
- CXX0052
- CAN0052
ms.assetid: 5060d479-d0a4-4682-b858-c8b9a4f324e6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0725d117f6481d2bdc218089a7599502c0f5213d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0052"></a>式エバリュエーター エラー CXX0052
メンバー関数がありません。  
  
 メンバー関数は、ブレークポイントとして指定されましたが、見つかりませんでした。 インライン展開されている関数にブレークポイントを設定と、このエラーが発生することができます。  
  
 使用してファイルを再コンパイル インライン展開を強制的に切断 (/Ob0) この関数にブレークポイントを設定します。  
  
 式には、定義されていない関数が呼び出されます。  
  
 このエラーは、can0052 と同じものと同じです。