---
title: "freelist クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- stdext::freelist
- freelist
- allocators/stdext::freelist
- allocators/stdext::freelist::pop
- allocators/stdext::freelist::push
dev_langs:
- C++
helpviewer_keywords:
- freelist class
ms.assetid: 8ad7e35c-4c80-4479-8ede-1a2497b06d71
caps.latest.revision: 17
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 2cff811e456e3cb47929080bef8203a8b89d02f9
ms.lasthandoff: 02/24/2017

---
# <a name="freelist-class"></a>freelist クラス
メモリ ブロックのリストを管理します。  
  
## <a name="syntax"></a>構文  
  
```
template <std::size_t Sz, class Max>  
class freelist
 : public Max
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`Sz`|割り当てられる配列内の要素の数。|  
|`Max`|フリー リストに格納される要素の最大数を示す最大クラス。 最大クラスは、[max_none](../standard-library/max-none-class.md)、[max_unbounded](../standard-library/max-unbounded-class.md)、[max_fixed_size](../standard-library/max-fixed-size-class.md)、[max_variable_size](../standard-library/max-variable-size-class.md) のいずれかにすることができます。|  
  
## <a name="remarks"></a>コメント  
 このテンプレート クラスは、サイズ `Sz` のメモリ ブロックのリストを管理します。リストの最大サイズは `Max` に渡される最大クラスによって決まります。  
  
### <a name="constructors"></a>コンストラクター  
  
|||  
|-|-|  
|[freelist](#freelist__freelist)|`freelist` 型のオブジェクトを構築します。|  
  
### <a name="member-functions"></a>メンバー関数  
  
|||  
|-|-|  
|[pop](#freelist__pop)|フリー リストから最初のメモリ ブロックを削除します。|  
|[push](#freelist__push)|メモリ ブロックをリストに追加します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<allocators>  
  
 **名前空間:** stdext  
  
##  <a name="freelist__freelist"></a>  freelist::freelist  
 `freelist` 型のオブジェクトを構築します。  
  
```
freelist();
```  
  
### <a name="remarks"></a>コメント  
  
##  <a name="freelist__pop"></a>  freelist::pop  
 フリー リストから最初のメモリ ブロックを削除します。  
  
```
void *pop();
```  
  
### <a name="return-value"></a>戻り値  
 一覧から削除するメモリ ブロックへのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 一覧が空の場合、メンバー関数は `NULL` を返します。 それ以外の場合は、空き一覧から最初のメモリ ブロックを削除します。  
  
##  <a name="freelist__push"></a>  freelist::push  
 メモリ ブロックをリストに追加します。  
  
```
bool push(void* ptr);
```  
  
### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`ptr`|フリー リストに追加するメモリ ブロックへのポインター。|  
  
### <a name="return-value"></a>戻り値  
 最大クラスの `full` 関数が `false` を返す場合は `true`、それ以外の場合、`push` 関数が `false` を返します。  
  
### <a name="remarks"></a>コメント  
 最大クラスの `full` 関数が `false` を返す場合、このメンバー関数は、`ptr` が指すメモリ ブロックをリストの先頭に追加します。  
  
## <a name="see-also"></a>関連項目  
 [\<allocators>](../standard-library/allocators-header.md)




