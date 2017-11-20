---
title: ".Ilk ファイルをリンカー入力として |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6e7d801992beb75ccc14e185fc062dc4c51f8433
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ilk-files-as-linker-input"></a>リンカー入力としての .ilk ファイル
インクリメンタル リンク、リンクは、最初のインクリメンタル リンク中に作成された .ilk ステータス ファイルを更新します。 このファイルは .exe ファイルまたは .dll ファイルと同じ基本名を持ち、拡張子は .ilk がします。 以降のインクリメンタル リンク中には、リンクは .ilk ファイルを更新します。 .Ilk ファイルが見つからない場合、リンクはフル リンクを実行し、新しい .ilk ファイルを作成します。 .Ilk ファイルが使用できない場合は、リンクはノンインクリメンタルのリンクを実行します。 インクリメンタル リンクに関する詳細については、次を参照してください。、[インクリメンタル リンク (/incremental)](../../build/reference/incremental-link-incrementally.md)オプション。  
  
## <a name="see-also"></a>関連項目  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)