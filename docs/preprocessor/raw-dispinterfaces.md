---
title: "raw_dispinterfaces |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: raw_dispinterfaces
dev_langs: C++
helpviewer_keywords: raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3d92c6940c4eabc83143ce1054604ae4648347d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="rawdispinterfaces"></a>raw_dispinterfaces
**C 固有の仕様**  
  
 ディスパッチインターフェイス メソッドおよびプロパティを呼び出すための低レベルのラッパー関数を生成するようにコンパイラに指示**idispatch::invoke**を返すと、`HRESULT`エラー コード。  
  
## <a name="syntax"></a>構文  
  
```  
raw_dispinterfaces  
```  
  
## <a name="remarks"></a>コメント  
 この属性を指定しない場合、高度なラッパーのみが生成され、エラーの場合は C++ 例外がスローされます。  
  
 **END C 固有の仕様**  
  
## <a name="see-also"></a>参照  
 [#import の属性](../preprocessor/hash-import-attributes-cpp.md)   
 [#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)