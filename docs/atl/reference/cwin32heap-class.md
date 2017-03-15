---
title: "CWin32Heap クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CWin32Heap
- ATL.CWin32Heap
- CWin32Heap
dev_langs:
- C++
helpviewer_keywords:
- CWin32Heap class
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
caps.latest.revision: 19
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 407f777b52529a333251c7d00481fdbfb14db619
ms.lasthandoff: 02/24/2017

---
# <a name="cwin32heap-class"></a>CWin32Heap クラス
このクラスは実装[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) Win32 ヒープ割り当て関数を使用します。  
  
> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。  
  
## <a name="syntax"></a>構文  
  
```
class CWin32Heap : public IAtlMemMgr
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CWin32Heap::CWin32Heap](#cwin32heap)|コンストラクターです。|  
|[CWin32Heap:: ~ CWin32Heap](#dtor)|デストラクターです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CWin32Heap::Allocate](#allocate)|ヒープ オブジェクトからメモリ ブロックを割り当てます。|  
|[Cwin32heap::attach](#attach)|既存のヒープには、ヒープのオブジェクトをアタッチします。|  
|[CWin32Heap::Detach](#detach)|既存のヒープからヒープ オブジェクトをデタッチします。|  
|[CWin32Heap::Free](#free)|以前は、ヒープから割り当てられたメモリを解放します。|  
|[CWin32Heap::GetSize](#getsize)|ヒープ オブジェクトから割り当てられたメモリ ブロックのサイズを返します。|  
|[CWin32Heap::Reallocate](#reallocate)|ヒープ オブジェクトからメモリ ブロックを再割り当てします。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CWin32Heap::m_bOwnHeap](#m_bownheap)|ヒープのハンドルの現在の所有権を決定するために使用するフラグです。|  
|[CWin32Heap::m_hHeap](#m_hheap)|ヒープのオブジェクトへのハンドルします。|  
  
## <a name="remarks"></a>コメント  
 `CWin32Heap`含む、Win32 ヒープ割り当て関数を使用してメモリの割り当て方法を実装する[選択肢](http://msdn.microsoft.com/library/windows/desktop/aa366597)と[など](http://msdn.microsoft.com/library/windows/desktop/aa366701)します。 その他のヒープ クラスとは異なり`CWin32Heap`メモリを割り当てる前に指定する有効なヒープ ハンドルが必要です。 プロセス ヒープを使用するその他のクラスの既定です。 コンス トラクターまたは、ハンドルを指定することができます、 [cwin32heap::attach](#attach)メソッドです。 参照してください、 [CWin32Heap::CWin32Heap](#cwin32heap)詳細についてはメソッドです。  
  
## <a name="example"></a>例  
 例を参照してください[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `IAtlMemMgr`  
  
 `CWin32Heap`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlmem.h  
  
##  <a name="a-nameallocatea--cwin32heapallocate"></a><a name="allocate"></a>CWin32Heap::Allocate  
 ヒープ オブジェクトからメモリ ブロックを割り当てます。  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `nBytes`  
 新しいメモリ ブロック内の要求されたバイト数。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックへのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 呼び出す[CWin32Heap::Free](#free)または[CWin32Heap::Reallocate](#reallocate)このメソッドによって割り当てられたメモリを解放します。  
  
 使用して実装[選択肢](http://msdn.microsoft.com/library/windows/desktop/aa366597)します。  
  
##  <a name="a-nameattacha--cwin32heapattach"></a><a name="attach"></a>Cwin32heap::attach  
 既存のヒープには、ヒープのオブジェクトをアタッチします。  
  
```
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `hHeap`  
 既存のヒープ ハンドル。  
  
 `bTakeOwnership`  
 フラグのどうかを示す、`CWin32Heap`オブジェクトがヒープのリソースに対する所有権を取得します。  
  
### <a name="remarks"></a>コメント  
 場合`bTakeOwnership`true で、`CWin32Heap`オブジェクトはヒープのハンドルの削除を担当します。  
  
##  <a name="a-namecwin32heapa--cwin32heapcwin32heap"></a><a name="cwin32heap"></a>CWin32Heap::CWin32Heap  
 コンストラクターです。  
  
```
CWin32Heap() throw();
CWin32Heap( HANDLE  hHeap) throw();
CWin32Heap(
    DWORD  dwFlags,
    size_t nInitialSize,
    size_t nMaxSize = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 `hHeap`  
 既存のヒープ オブジェクト。  
  
 `dwFlags`  
 ヒープの作成に使用されるフラグ。  
  
 *nInitialSize*  
 ヒープの初期サイズ。  
  
 `nMaxSize`  
 ヒープの最大サイズ。  
  
### <a name="remarks"></a>コメント  
 メモリを割り当てる前に、`CWin32Heap` オブジェクトに有効なヒープ ハンドルを提供する必要があります。 これを実現する最も簡単な方法は、プロセス ヒープを使用することです。  
  
 [!code-cpp[NVC_ATL_Utilities #&92;](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]  
  
 また、コンストラクターに既存のヒープ ハンドルを提供できますが、その場合には新しいオブジェクトはヒープの所有権を引き継ぎません。 `CWin32Heap` オブジェクトが削除されても、元のヒープ ハンドルは依然として有効です。  
  
 既存のヒープは、新しい添付することもオブジェクトを使用して[cwin32heap::attach](#attach)します。  
  
 すべての処理がシングル スレッドから行われるときに、ヒープが必要な場合、最適な方法は次のようにオブジェクトを作成することです。  
  
 [!code-cpp[NVC_ATL_Utilities #&93;](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]  
  
 パラメーター **HEAP_NO_SERIALIZE**ヒープ関数の割り当てし、パフォーマンスがそれに対応の向上と、メモリを解放するときに相互排他を使用しないを指定します。  
  
 第 3 のパラメーターの既定値は 0 であり、この場合には必要に応じてヒープを拡大できます。 参照してください[HeapCreate](http://msdn.microsoft.com/library/windows/desktop/aa366599\(v=vs.85\).aspx)メモリ サイズおよびフラグの詳細についてです。  
  
##  <a name="a-namedtora--cwin32heapcwin32heap"></a><a name="dtor"></a>CWin32Heap:: ~ CWin32Heap  
 デストラクターです。  
  
```
~CWin32Heap() throw();
```  
  
### <a name="remarks"></a>コメント  
 場合に、ヒープのハンドルを破棄、`CWin32Heap`オブジェクトがヒープの所有権を持っています。  
  
##  <a name="a-namedetacha--cwin32heapdetach"></a><a name="detach"></a>CWin32Heap::Detach  
 既存のヒープからヒープ オブジェクトをデタッチします。  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトをアタッチすると以前のヒープのハンドルを返します。  
  
##  <a name="a-namefreea--cwin32heapfree"></a><a name="free"></a>CWin32Heap::Free  
 以前、ヒープから割り当てられたメモリを解放[CWin32Heap::Allocate](#allocate)または[CWin32Heap::Reallocate](#reallocate)します。  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 解放するメモリ ブロックへのポインター。 NULL は有効な値であり、何も行われません。  
  
##  <a name="a-namegetsizea--cwin32heapgetsize"></a><a name="getsize"></a>CWin32Heap::GetSize  
 ヒープ オブジェクトから割り当てられたメモリ ブロックのサイズを返します。  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 サイズを取得するメモリ ブロックへのポインター。 これによって返されたポインターは、 [CWin32Heap::Allocate](#allocate)または[CWin32Heap::Reallocate](#reallocate)します。  
  
### <a name="return-value"></a>戻り値  
 割り当てられたメモリ ブロックのバイト単位のサイズを返します。  
  
##  <a name="a-namembownheapa--cwin32heapmbownheap"></a><a name="m_bownheap"></a>CWin32Heap::m_bOwnHeap  
 格納されているヒープ ハンドルの現在の所有権を決定するために使用するフラグ[m_hHeap](#m_hheap)します。  
  
```
bool m_bOwnHeap;
```  
  
##  <a name="a-namemhheapa--cwin32heapmhheap"></a><a name="m_hheap"></a>CWin32Heap::m_hHeap  
 ヒープのオブジェクトへのハンドルします。  
  
```
HANDLE m_hHeap;
```  
  
### <a name="remarks"></a>コメント  
 ヒープのオブジェクトへのハンドルを格納する変数。  
  
##  <a name="a-namereallocatea--cwin32heapreallocate"></a><a name="reallocate"></a>CWin32Heap::Reallocate  
 ヒープ オブジェクトからメモリ ブロックを再割り当てします。  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 再割り当てするメモリ ブロックへのポインター。  
  
 `nBytes`  
 割り当てられるブロックの新しいサイズ (バイト単位)。 ブロックは大きくすることも小さくすることもできます。  
  
### <a name="return-value"></a>戻り値  
 新しく割り当てられたメモリ ブロックへのポインターを返します。  
  
### <a name="remarks"></a>コメント  
 場合`p`が NULL の場合、するメモリ ブロックがまだ割り当てられていないことが前提とし、 [CWin32Heap::Allocate](#allocate)の引数を指定して呼び出されます`nBytes`します。  
  
## <a name="see-also"></a>関連項目  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [クラス](../../atl/reference/iatlmemmgr-class.md)   
 [CLocalHeap クラス](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap クラス](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap クラス](../../atl/reference/ccrtheap-class.md)   
 [CComHeap クラス](../../atl/reference/ccomheap-class.md)

