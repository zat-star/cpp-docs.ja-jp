---
title: "region、endregion |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
dev_langs:
- C++
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1fda2aba5fdb0aa83066c1762822bfce5fc5f6b4
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="region-endregion"></a>region、endregion
**#pragma region** 、コードのブロックを展開したり折りたたんだりを使用する場合を指定することができます、[アウトライン機能](/visualstudio/ide/outlining)の Visual Studio コード エディター。  
  
## <a name="syntax"></a>構文  
  
```  
#pragma region name  
#pragma endregion comment  
```  
  
#### <a name="parameters"></a>パラメーター  
 `comment`(省略可能)  
 コード エディターに表示されるコメント。  
  
 *名前*(省略可能)  
 領域の名前。  この名前はコード エディターに表示されます。  
  
## <a name="remarks"></a>コメント  
 **#pragma endregion**の末尾を示す、 **#pragma region**ブロックします。  
  
 A`#region`でブロックを終了する必要があります**#pragma endregion**です。  
  
## <a name="example"></a>例  
  
```  
// pragma_directives_region.cpp  
#pragma region Region_1  
void Test() {}  
void Test2() {}  
void Test3() {}  
#pragma endregion Region_1  
  
int main() {}  
```  
  
## <a name="see-also"></a>参照  
 [プラグマ ディレクティブと __Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)