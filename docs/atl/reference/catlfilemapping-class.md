---
title: "CAtlFileMapping クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
dev_langs:
- C++
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
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
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 2693647af904eab1ed0f84bc406bc1207d4a9b8c
ms.lasthandoff: 02/24/2017

---
# <a name="catlfilemapping-class"></a>CAtlFileMapping クラス
このクラスのメソッドへのキャスト演算子の追加メモリ マップト ファイルを表します。 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T = char>  
class CAtlFileMapping : public CAtlFileMappingBase
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 キャスト演算子を使用するデータの型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CAtlFileMapping::operator T *](#operator_t_star)|により、暗黙の変換の`CAtlFileMapping`オブジェクトを`T` ** \***します。|  
  
## <a name="remarks"></a>コメント  
 このクラスの暗黙的な変換を許可するように単一のキャスト演算子を追加する`CAtlFileMapping`オブジェクトを`T` ** \***します。 その他のメンバーが基底クラスによって提供される[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlfile.h  
  
##  <a name="operator_t_star"></a>CAtlFileMapping::operator T *  
 により、暗黙の変換の`CAtlFileMapping`オブジェクトを`T` ** \***します。  
  
```  
operator T*() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。、 `T` ** \* **メモリ マップト ファイルの先頭へのポインター。  
  
### <a name="remarks"></a>コメント  
 呼び出し[CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata)として返されたポインターとして再解釈と、 `T` ** \* ** 、 *T*はこのクラスのテンプレート パラメーターとして使用される型です。  
  
## <a name="see-also"></a>関連項目  
 [CAtlFileMappingBase クラス](../../atl/reference/catlfilemappingbase-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)

