---
title: ".リンカー入力として res ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- RES files as linker input
- .res files as linker input
- linking [C++], resource files
- resource files, linking
ms.assetid: 9c37ab00-97df-4d9a-91cd-6bf132970683
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b8b4a1b69887033ca0c8cccf3e4b9eb193ee41d9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="res-files-as-linker-input"></a>リンカー入力としての .res ファイル
プログラムをリンクするときに、.res ファイルを指定できます。 リソース コンパイラ (RC) では、.res ファイルが作成されます。 リンクは、COFF に .res ファイルを自動的に変換します。 CVTRES.exe ツールは、LINK.exe と同じディレクトリか、PATH 環境変数で指定されたディレクトリにする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [LINK の入力ファイル](../../build/reference/link-input-files.md)   
 [リンカー オプション](../../build/reference/linker-options.md)