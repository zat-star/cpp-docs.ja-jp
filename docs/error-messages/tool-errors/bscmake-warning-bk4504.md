---
title: "BSCMAKE の警告 BK4504 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK4504
dev_langs: C++
helpviewer_keywords: BK4504
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f7f6d854fbd74d9ca05ba6797bbd57db52b7a70e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-warning-bk4504"></a>BSCMAKE の警告 BK4504
ファイルには、参照が多すぎます; が含まれています。このソースからさらに参照は無視されます。  
  
 .Cpp ファイルには、複数の 64,000 シンボル参照が含まれています。 BSCMAKE では、ファイルで 64,000 の参照が発生しました、ときにそれ以上のすべての参照は無視されます。  
  
 問題を修正する 2 つのファイルに分割またはより少ない 64,000 を持つ他のファイルのシンボル参照、またはを使用して、`#pragma component(browser)`プリプロセッサ ディレクティブの特定の参照に対して生成されるシンボルを制限します。 詳細については、次を参照してください。[コンポーネント](../../preprocessor/component.md)です。