---
title: "リンカー ツールの警告 LNK4010 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4010
dev_langs:
- C++
helpviewer_keywords:
- LNK4010
ms.assetid: 2824cf99-4174-4b60-a6e2-c01e9f1ee52d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 79f52338eea40c42cacf8b0880afe42b75037abc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4010"></a>リンカー ツールの警告 LNK4010
無効なサブシステム バージョン番号番号です。既定のサブシステムのバージョンと見なされます  
  
 イメージのサブシステムのバージョンを指定することができます ([/SUBSYSTEM](../../build/reference/subsystem-specify-subsystem.md))。 各サブシステムには、最小バージョン要件があります。 指定されたバージョンが、最小値よりも小さい場合は、この警告が発生し、リンカーが既定のサブシステムを使用するだけです。