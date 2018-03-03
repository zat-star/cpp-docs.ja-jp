---
title: "依存ファイルのパスを検索 |Microsoft ドキュメント"
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
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6093db4ac8e0c88dfe6e4b5a5463e5ee8d24349
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="search-paths-for-dependents"></a>依存ファイルの検索パス
各依存ファイルには、次のように指定された、省略可能な検索パスがあります。  
  
## <a name="syntax"></a>構文  
  
```  
{directory[;directory...]}dependent  
```  
  
## <a name="remarks"></a>コメント  
 (Nmake の) は、現在のディレクトリでは、最初にし、指定された順序内のディレクトリで依存関係を検索します。 マクロには、検索パスの一部またはすべてを指定できます。 ディレクトリ名を囲む中かっこ ({});複数のディレクトリをセミコロン (;) で区切ります。 スペースまたはタブは許可されません。  
  
## <a name="see-also"></a>参照  
 [依存](../build/dependents.md)