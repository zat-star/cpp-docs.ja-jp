---
title: "リソース コンパイラの警告 RW4004 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RW4004
dev_langs: C++
helpviewer_keywords: RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aedc73ddc2934cf44ae5ebf98cf0e4e50814feb9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="resource-compiler-warning-rw4004"></a>リソース コンパイラの警告 RW4004
仮想キー コードに相当しない ASCII 文字  
  
 VIRTKEY 型アクセラレータの仮想キー コードに文字列リテラルが使用されました。  
  
 この警告では、処理を続行できますが、生成されたアクセラレータ キーが指定した文字列と一致しない可能性があることに注意してください。 (VIRTKEY は、ASCII アクセラレータとは異なるキー コードを使用します。)  
  
 使用して、アクセラレータを取得することを確認する文字列リテラルは構文的に有効ですが、のみことができます、 **vk _\* #define** WINDOWS.h 内の値。