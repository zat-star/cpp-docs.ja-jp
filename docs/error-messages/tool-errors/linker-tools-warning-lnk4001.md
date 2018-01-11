---
title: "リンカー ツールの警告 LNK4001 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4001
dev_langs: C++
helpviewer_keywords: LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2ecc78fe50fd34a0c6f583bf103d368e23f19f2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4001"></a>リンカー ツールの警告 LNK4001
オブジェクト ファイルが指定されていません。ライブラリを使用します  
  
 リンカーが渡されましたが、1 つまたは複数の .lib ファイル、.obj ファイルがありません。  
  
 リンカーは、.obj ファイルにアクセスすることである .lib ファイル内の情報にアクセスできないために、この警告は、その他のリンカー オプションを明示的に指定する必要があるを示します。 たとえばを指定する必要があります、[マシン/](../../build/reference/machine-specify-target-platform.md)、 [/out](../../build/reference/out-output-file-name.md)、または[/ENTRY](../../build/reference/entry-entry-point-symbol.md)オプション。