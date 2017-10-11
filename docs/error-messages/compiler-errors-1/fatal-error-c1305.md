---
title: "致命的なエラー C1305 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1305
dev_langs:
- C++
helpviewer_keywords:
- C1305
ms.assetid: 1629c850-e2db-4678-83d8-9bfc85323bc5
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cf4a9025b8d441ae42b7de7605594fda60dc5603
ms.contentlocale: ja-jp
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1305"></a>致命的なエラー C1305
プロファイル データベース 'pgd_fil' は異なるアーキテクチャ用です。  
  
 渡された別のプラットフォーム用に/LTCG:PGINSTRUMENT 操作から生成された .pgd ファイル[/LTCG:PGOPTIMIZE](../../build/reference/ltcg-link-time-code-generation.md)です。 [プロファイル ガイド付き最適化の](../../build/reference/profile-guided-optimizations.md)x86 のものがあると[!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]プラットフォームです。 ただし、あるプラットフォーム用に /LTCG:PGINSTRUMENT 操作によって生成された .pgd ファイルを、別のプラットフォームの /LTCG:PGOPTIMIZE への入力として使用することはできません。  
  
 このエラーを解決するには、/LTCG:PGINSTRUMENT で作成された .pgd ファイルを同じプラットフォームの /LTCG:PGOPTIMIZE に渡します。
