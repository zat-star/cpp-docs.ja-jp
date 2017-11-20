---
title: "擬似ターゲット |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b018cd586e48f344b93b31571ba60ae9982ad4fe
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="pseudotargets"></a>疑似ターゲット
疑似ターゲットは、依存関係行で、ファイル名の代わりに使用されるラベルです。 ファイルが存在しない、古いとして解釈されます。 (Nmake の) では、疑似ターゲットのタイムスタンプは、一番最近のすべての依存関係の前提としています。 依存関係を持たない、現在の時刻と見なされます。 疑似ターゲットがターゲットとして使用されている場合、そのコマンドが常に実行します。 疑似ターゲット依存関係として使用する必要があります、別の依存関係のターゲットとしても表示されます。 ただし、その依存関係はコマンド ブロックする必要はありません。  
  
 疑似ターゲットの名前では、対象のファイル名の構文規則に従います。 ただし、名前に拡張子がない場合 (つまりはピリオドを含まない)、そのファイル名の最大 8 文字を超えることがあり、最大 256 文字まで使用できます。  
  
## <a name="see-also"></a>関連項目  
 [ターゲット](../build/targets.md)