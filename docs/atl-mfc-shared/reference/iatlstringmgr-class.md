---
title: "IAtlStringMgr クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAtlStringMgr
dev_langs:
- C++
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
caps.latest.revision: 16
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
ms.openlocfilehash: 4ff4aa01a6d30f377560962f98a5892bdcc37837
ms.lasthandoff: 02/24/2017

---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr クラス
このクラスにインターフェイスを表します。、`CStringT`メモリ マネージャー。  
  
## <a name="syntax"></a>構文  
  
```
__interface IAtlStringMgr
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[割り当てる](#allocate)|新しい文字列データ構造体を割り当てるには、このメソッドを呼び出します。|  
|[複製](#clone)|別のインスタンスで使用するための新しい文字列マネージャーへのポインターを返すには、このメソッドを呼び出す`CSimpleStringT`します。|  
|[無料](#free)|文字列データの構造体を解放するには、このメソッドを呼び出します。|  
|[GetNilString](#getnilstring)|ポインターを返す、`CStringData`空の文字列オブジェクトを使用するオブジェクト。|  
|[再割り当てください。](#reallocate)|文字列データ構造を再割り当てするには、このメソッドを呼び出します。|  
  
## <a name="remarks"></a>コメント  
 このインターフェイスは、MFC に依存しない文字列クラスによって使用されるメモリを管理します。など、 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)、 [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)、および[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)します。  
  
 このクラスは、カスタム文字列クラスに対してカスタム メモリ マネージャーの実装も使用できます。 詳細については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpstr.h  
  
##  <a name="a-nameallocatea--iatlstringmgrallocate"></a><a name="allocate"></a>IAtlStringMgr::Allocate  
 新しい文字列データ構造体が割り当てられます。  
  
```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nAllocLength`  
 新しいメモリ ブロック内の文字の数。  
  
 `nCharSize`  
 文字列のマネージャーによって使用される文字型のサイズをバイト単位で。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックへのポインターを返します。  
  
> [!NOTE]
>  例外をスローして失敗した割り当てを通知できません。 失敗した割り当てを返すことによって通知される代わりに、 **NULL**します。  
  
### <a name="remarks"></a>コメント  
 呼び出す[IAtlStringMgr::Free](#free)または[IAtlStringMgr::ReAllocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
##  <a name="a-nameclonea--iatlstringmgrclone"></a><a name="clone"></a>IAtlStringMgr::Clone  
 別のインスタンスで使用するための新しい文字列マネージャーへのポインターを返します`CSimpleStringT`します。  
  
```
IAtlStringMgr* Clone() throw();
```  
  
### <a name="return-value"></a>戻り値  
 コピーを返す、`IAtlStringMgr`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 よく文字列マネージャーが新しい文字列の必要なときに、フレームワークが呼び出します。 ほとんどの場合、**この**ポインターが返されます。  
  
 ただし、メモリ マネージャーでの複数のインスタンスによって使用されているがサポートされていない場合`CSimpleStringT`、共有可能な文字列マネージャーへのポインターを返す必要があります。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
##  <a name="a-namefreea--iatlstringmgrfree"></a><a name="free"></a>IAtlStringMgr::Free  
 文字列データの構造体を解放します。  
  
```
void Free(CStringData* pData) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pData`  
 解放するメモリ ブロックへのポインター。  
  
### <a name="remarks"></a>コメント  
 割り当てられている指定されたメモリ ブロックを解放[Allocate](#allocate)または[再割り当て](../../atl/reference/iatlmemmgr-class.md#reallocate)します。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
##  <a name="a-namegetnilstringa--iatlstringmgrgetnilstring"></a><a name="getnilstring"></a>IAtlStringMgr::GetNilString  
 空の文字列の文字列データの構造体へのポインターを返します。  
  
```
CStringData* GetNilString() throw();
```  
  
### <a name="return-value"></a>戻り値  
 ポインター、`CStringData`オブジェクトが空の文字列を表すために使用します。  
  
### <a name="remarks"></a>コメント  
 空の文字列表現を取得するには、この関数を呼び出します。  
  
> [!NOTE]
>  カスタム文字列マネージャーを実装するときにこの関数は失敗する必要があることはありません。 インスタンスを埋め込むことによってこれを確認できる**CNilStringData**文字列 manager: クラス、およびそのインスタンスへのポインターを返す。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
##  <a name="a-namereallocatea--iatlstringmgrreallocate"></a><a name="reallocate"></a>IAtlStringMgr::Reallocate  
 文字列データ構造を再割り当てします。  
  
```
CStringData* Reallocate(  
 CStringData* pData,
 int nAllocLength,
 int nCharSize) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `pData`  
 メモリ マネージャーによって以前に割り当てられたメモリへのポインター。  
  
 `nAllocLength`  
 新しいメモリ ブロック内の文字の数。  
  
 `nCharSize`  
 文字列のマネージャーによって使用される文字型のサイズをバイト単位で。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックの先頭へのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 指定された既存のメモリ ブロックのサイズを変更するには、この関数を呼び出す`pData`します。  
  
 呼び出す[IAtlStringMgr::Free](#free)このメソッドによって割り当てられたメモリを解放します。  
  
> [!NOTE]
>  使用例については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL と MFC クラスの共有](../../atl-mfc-shared/atl-mfc-shared-classes.md)



