---
title: "CStringData クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringData
- ATLSIMPSTR/ATL::CStringData
- ATLSIMPSTR/ATL::AddRef
- ATLSIMPSTR/ATL::data
- ATLSIMPSTR/ATL::IsLocked
- ATLSIMPSTR/ATL::IsShared
- ATLSIMPSTR/ATL::Lock
- ATLSIMPSTR/ATL::Release
- ATLSIMPSTR/ATL::Unlock
- ATLSIMPSTR/ATL::nAllocLength
- ATLSIMPSTR/ATL::nDataLength
- ATLSIMPSTR/ATL::nRefs
- ATLSIMPSTR/ATL::pStringMgr
dev_langs:
- C++
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b7dfebebbec7acc774fa2e63ab9fafed788f679a
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cstringdata-class"></a>CStringData クラス
このクラスは、文字列オブジェクトのデータを表します。  
  
## <a name="syntax"></a>構文  
  
```
struct CStringData
```  
  
## <a name="members"></a>メンバー  
  
### <a name="methods"></a>メソッド  
  
|||  
|-|-|  
|[AddRef](#addref)|文字列データ オブジェクトの参照カウントをインクリメントします。|  
|[data](#data)|文字列オブジェクトの文字データを取得します。|  
|[IsLocked](#islocked)|関連付けられている文字列オブジェクトのバッファーがロックされているかどうかを判断します。|  
|[とき](#isshared)|関連付けられている文字列オブジェクトのバッファーが共有されているかどうかを判断します。|  
|[ロック](#lock)|関連付けられている文字列オブジェクトのバッファーをロックします。|  
|[Release](#release)|指定された文字列オブジェクトを解放します。|  
|[ロックを解除します。](#unlock)|関連付けられている文字列オブジェクトのバッファーのロックを解除します。|  
  
### <a name="data-members"></a>データ メンバー  
  
|||  
|-|-|  
|[nAllocLength](#nalloclength)|割り当てられているデータの長さ`XCHAR`(終端の null) を含むいない s|  
|[nDataLength](#ndatalength)|現在使用されているデータの長さ`XCHAR`(終端の null) を含むいない s|  
|[nRefs](#nrefs)|オブジェクトの現在の参照カウントします。|  
|[pStringMgr](#pstringmgr)|この文字列オブジェクトの文字列マネージャーへのポインター。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、カスタム文字列マネージャーを実装している開発者でのみ使用する必要があります。 カスタム文字列マネージャーの詳細については、次を参照してください[メモリ管理と CStringT。](../../atl-mfc-shared/memory-management-with-cstringt.md)  
  
 このクラスは、さまざまな種類の情報およびなどの上位の文字列オブジェクトに関連付けられたデータをカプセル化[CStringT](../../atl-mfc-shared/reference/cstringt-class.md)、 [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)、または[CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)のオブジェクト。 上位のすべての文字列オブジェクトがそれに関連するへのポインターを含む`CStringData`の複数の文字列オブジェクトを同一の文字列データ オブジェクトを指すようにするオブジェクト。 このリレーションシップは、参照カウントによって表されます ( `nRefs`) の`CStringData`オブジェクトです。  
  
> [!NOTE]
>  特定の場合、文字列型 (など**CFixedString**) は、上位&2; つ以上の文字列オブジェクトを文字列データ オブジェクトを共有していません。 これに関する詳細については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
 このデータで構成されます。  
  
-   メモリ マネージャー (型の[IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)) の文字列です。  
  
-   現在の長さ ( [nDataLength](#ndatalength)) の文字列です。  
  
-   割り当て済みの長さ ( [nAllocLength](#nalloclength)) の文字列です。 パフォーマンス上の理由から、これとは異なる現在の文字列の長さ  
  
-   現在の参照カウント ( [nRefs](#nrefs)) の`CStringData`オブジェクトです。 この値は文字列オブジェクトの数は同じ共有を決定する際に使用`CStringData`オブジェクトです。  
  
-   実際の文字バッファー ([データ](#data)) の文字列です。  
  
    > [!NOTE]
    >  文字列オブジェクトの実際の文字バッファー文字列マネージャーが割り当てられるし、に追加されますが、`CStringData`オブジェクトです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlsimpstr.h  
  
##  <a name="addref"></a>CStringData::AddRef  
 文字列オブジェクトの参照カウントをインクリメントします。  
  
```
void AddRef() throw();
```  
  
### <a name="remarks"></a>コメント  
 文字列オブジェクトの参照カウントをインクリメントします。  
  
> [!NOTE]
>  負の数は、文字列バッファーがロックされていることを示すために、負の値の参照カウントを含む文字列でこのメソッドを呼び出さないでください。  
  
##  <a name="data"></a>CStringData::data  
 文字列オブジェクトの文字バッファーへのポインターを返します。  
  
```
void* data() throw();
```  
  
### <a name="return-value"></a>戻り値  
 文字列オブジェクトの文字バッファーへのポインター。  
  
### <a name="remarks"></a>コメント  
 この関数では、関連付けられている文字列オブジェクトの現在の文字バッファーを返します。  
  
> [!NOTE]
>  このバッファーはによって割り当てられず、`CStringData`オブジェクトが必要なときに、文字列マネージャーによってです。 割り当てられると、バッファーが文字列データ オブジェクトに追加されます。  
  
##  <a name="islocked"></a>CStringData::IsLocked  
 文字バッファーがロックされているかどうかを判断します。  
  
```
bool IsLocked() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**バッファーがロックされている、それ以外の場合**false**します。  
  
### <a name="remarks"></a>コメント  
 文字列オブジェクトの文字バッファーが現在ロックされているかどうかを判断するには、この関数を呼び出します。  
  
##  <a name="isshared"></a>CStringData::IsShared  
 文字バッファーを共有するかどうかを判断します。  
  
```
bool IsShared() const throw();
```  
  
### <a name="return-value"></a>戻り値  
 返します。 **true**場合は、バッファーが共有されているそれ以外の場合**false**します。  
  
### <a name="remarks"></a>コメント  
 文字列データ オブジェクトの文字バッファーが複数の文字列オブジェクトの間で共有されているかどうかを判断するには、この関数を呼び出します。  
  
##  <a name="lock"></a>CStringData::Lock  
 関連付けられている文字列オブジェクトの文字バッファーをロックします。  
  
```
void Lock() throw();
```  
  
### <a name="remarks"></a>コメント  
 文字列データ オブジェクトの文字バッファーをロックするには、この関数を呼び出します。 ロックおよびロック解除は、開発者が文字バッファーへの直接アクセスが必要な場合に使用されます。 ロックの良い例に示すは、 [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer)と[として](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer)メソッドの`CSimpleStringT`です。  
  
> [!NOTE]
>  バッファーが上位の文字列オブジェクトの間で共有されていない場合のみ、文字バッファーをロックできます。  
  
##  <a name="nalloclength"></a>CStringData::nAllocLength  
 割り当てられた文字バッファーの長さです。  
  
```
int nAllocLength;
```  
  
### <a name="remarks"></a>コメント  
 割り当てられているデータのバッファーの長さを格納`XCHAR`s (終端の null) などではありません。  
  
##  <a name="ndatalength"></a>CStringData::nDataLength  
 現在の文字列オブジェクトの長さ。  
  
```
int nDataLength;
```  
  
### <a name="remarks"></a>コメント  
 現在使用されているデータの長さを格納`XCHAR`s (終端の null) などではありません。  
  
##  <a name="nrefs"></a>CStringData::nRefs  
 文字列データ オブジェクトの参照カウント。  
  
```
long nRefs;
```  
  
### <a name="remarks"></a>コメント  
 文字列データ オブジェクトの参照カウントを格納します。 この数は、文字列データ オブジェクトに関連付けられている上位の文字列オブジェクトの数を示します。 負の値は、文字列データ オブジェクトが現在ロックされていることを示します。  
  
##  <a name="pstringmgr"></a>CStringData::pStringMgr  
 関連付けられている文字列オブジェクトのメモリ マネージャー。  
  
```
IAtlStringMgr* pStringMgr;
```  
  
### <a name="remarks"></a>コメント  
 関連付けられている文字列オブジェクトのメモリ マネージャーが格納されます。 メモリ マネージャーと文字列の詳細については、次を参照してください。[メモリ管理と CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)します。  
  
##  <a name="release"></a>CStringData::Release  
 文字列データ オブジェクトの参照カウントをデクリメントします。  
  
```
void Release() throw();
```  
  
### <a name="remarks"></a>コメント  
 参照カウントをデクリメントするためには、この関数を呼び出して解放、`CStringData`参照カウントがゼロに達する場合に構造化します。 文字列オブジェクトが削除され、そのため、文字列データ オブジェクトを参照する必要はなくなりますこれは一般的です。  
  
 たとえば、次のコードは呼び出します`CStringData::Release`文字列データ オブジェクトに関連付けられたの`str1`:  
  
 [!code-cpp[NVC_ATLMFC_Utilities #&104;](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]  
  
##  <a name="unlock"></a>CStringData::Unlock  
 関連付けられている文字列オブジェクトの文字バッファーをロック解除します。  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>コメント  
 文字列データ オブジェクトの文字バッファーのロックを解除するには、この関数を呼び出します。 バッファーはロックされているが、共有可能であるし、参照をカウントできます。  
  
> [!NOTE]
>  各呼び出し`Lock`に対応する呼び出しに一致する必要がある`Unlock`です。  
  
 ロックおよびロック解除は、開発者は、文字列データを共有しないことを確認する必要があるときに使用されます。 ロックの良い例に示すは、 [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer)と[として](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer)メソッドの`CSimpleStringT`です。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [ATL と MFC クラスの共有](../../atl-mfc-shared/atl-mfc-shared-classes.md)



