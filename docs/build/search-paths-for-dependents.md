---
title: "依存ファイルのパスを検索 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: cf777c89c78ab844b61138c30a5a9a25ca6b91d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="search-paths-for-dependents"></a>依存ファイルの検索パス
各依存ファイルには、次のように指定された、省略可能な検索パスがあります。  
  
## <a name="syntax"></a>構文  
  
```  
{directory[;directory...]}dependent  
```  
  
## <a name="remarks"></a>コメント  
 (Nmake の) は、現在のディレクトリでは、最初にし、指定された順序内のディレクトリで依存関係を検索します。 マクロには、検索パスの一部またはすべてを指定できます。 ディレクトリ名を囲む中かっこ ({});複数のディレクトリをセミコロン (;) で区切ります。 スペースまたはタブは許可されません。  
  
## <a name="see-also"></a>関連項目  
 [依存](../build/dependents.md)