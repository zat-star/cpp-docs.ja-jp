---
title: "擬似ターゲット |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- makefiles, pseudotargets
- pseudotargets and NMAKE
- NMAKE program, pseudotargets
- timestamps, makefile pseudotargets
- NMAKE program, targets
ms.assetid: c8c479dc-0129-4186-8366-bc6251f2b494
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 761b71f05840c86516563df79d45cc1bb018fbba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="pseudotargets"></a>疑似ターゲット
疑似ターゲットは、依存関係行で、ファイル名の代わりに使用されるラベルです。 ファイルが存在しない、古いとして解釈されます。 (Nmake の) では、疑似ターゲットのタイムスタンプは、一番最近のすべての依存関係の前提としています。 依存関係を持たない、現在の時刻と見なされます。 疑似ターゲットがターゲットとして使用されている場合、そのコマンドが常に実行します。 疑似ターゲット依存関係として使用する必要があります、別の依存関係のターゲットとしても表示されます。 ただし、その依存関係はコマンド ブロックする必要はありません。  
  
 疑似ターゲットの名前では、対象のファイル名の構文規則に従います。 ただし、名前に拡張子がない場合 (つまりはピリオドを含まない)、そのファイル名の最大 8 文字を超えることがあり、最大 256 文字まで使用できます。  
  
## <a name="see-also"></a>参照  
 [ターゲット](../build/targets.md)