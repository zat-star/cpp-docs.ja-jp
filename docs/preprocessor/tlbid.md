---
title: "tlbid |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- tlbid
dev_langs:
- C++
helpviewer_keywords:
- tlbid attribute
ms.assetid: 54b06785-191b-4e77-a9a5-485f2b4acb09
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 52cb9237537e151e699974fe91c5a7a99725513f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="tlbid"></a>tlbid
**C 固有の仕様**  
  
 プライマリ タイプ ライブラリ以外のライブラリの読み込みを許可します。  
  
## <a name="syntax"></a>構文  
  
```  
tlbid(number)  
```  
  
#### <a name="parameters"></a>パラメーター  
 `number`  
 `filename` のタイプ ライブラリの番号。  
  
## <a name="remarks"></a>コメント  
 複数のタイプ ライブラリが 1 つの DLL に組み込まれている場合、`tlbid` を使用してプライマリ タイプ ライブラリ以外のライブラリを読み込むことができます。  
  
 例:  
  
```  
#import <MyResource.dll> tlbid(2)  
```  
  
 上の式は、下の式と同等です。  
  
```  
LoadTypeLib("MyResource.dll\\2");  
```  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>参照  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)