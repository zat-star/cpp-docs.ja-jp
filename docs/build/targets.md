---
title: "ターゲット |Microsoft ドキュメント"
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
- targets, specifying in NMAKE
ms.assetid: 826ee849-4278-4c6e-97c3-79a2b5fe6463
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a07947dc7de4529d8cef3aa0f104d529d0b95ea5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="targets"></a>ターゲット
依存関係行で、有効なファイル名、ディレクトリ名を使用して、1 つまたは複数のターゲットを指定または[疑似ターゲット](../build/pseudotargets.md)です。 1 つ以上のスペースまたはタブで複数のターゲットを区切ります。 ターゲットは、大文字と小文字が区別されません。 ファイル名を持つ、パスを指定します。 ターゲットは、256 文字を超えることはできません。 コロンの前のターゲットが 1 つの文字の場合は、区切るスペース; を使用してください。それ以外の場合 (nmake の) は、ドライブ指定子として文字とコロンの組み合わせを解釈します。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
 [擬似ターゲット](../build/pseudotargets.md)  
  
 [複数のターゲット](../build/multiple-targets.md)  
  
 [依存関係](../build/cumulative-dependencies.md)  
  
 [複数の記述ブロック内のターゲット](../build/targets-in-multiple-description-blocks.md)  
  
 [依存関係の副作用](../build/dependency-side-effects.md)  
  
## <a name="see-also"></a>参照  
 [記述ブロック](../build/description-blocks.md)