---
title: "リンカー ツールの警告 LNK4001 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4001
dev_langs:
- C++
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 7c00778af6740f1941b8f62836d4a169a1ca8f6b
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4001"></a>リンカー ツールの警告 LNK4001
オブジェクト ファイルが指定されていません。ライブラリを使用します。  
  
 リンカーが渡されましたが、1 つまたは複数の .lib ファイル、.obj ファイルがありません。  
  
 リンカーが .obj ファイルにアクセスすることは、.lib ファイル内の情報にアクセスできないため、この警告は、その他のリンカー オプションを明示的に指定する必要があるを示します。 など、指定する必要があります、[マシン/](../../build/reference/machine-specify-target-platform.md)、 [/out](../../build/reference/out-output-file-name.md)、または[/ENTRY](../../build/reference/entry-entry-point-symbol.md)オプション。
