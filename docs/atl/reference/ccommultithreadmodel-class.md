---
title: "CComMultiThreadModel クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel
- ATLBASE/ATL::CComMultiThreadModel::AutoCriticalSection
- ATLBASE/ATL::CComMultiThreadModel::CriticalSection
- ATLBASE/ATL::CComMultiThreadModel::ThreadModelNoCS
- ATLBASE/ATL::CComMultiThreadModel::Decrement
- ATLBASE/ATL::CComMultiThreadModel::Increment
dev_langs:
- C++
helpviewer_keywords:
- ATL, multithreading
- CComMultiThreadModel class
- threading [ATL]
ms.assetid: db8f1662-2f7a-44b3-b341-ffbfb6e422a3
caps.latest.revision: 21
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 6dbfb33a717b23e8252c9bcb2fc11b4a6e420280
ms.lasthandoff: 02/24/2017

---
# <a name="ccommultithreadmodel-class"></a>CComMultiThreadModel クラス
`CComMultiThreadModel`インクリメントおよびデクリメントするため、変数の値に対応するスレッド セーフであるメソッドを提供します。  
  
## <a name="syntax"></a>構文  
  
```
class CComMultiThreadModel
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)|クラスを参照[CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md)します。|  
|[CComMultiThreadModel::CriticalSection](#criticalsection)|クラスを参照[CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)します。|  
|[CComMultiThreadModel::ThreadModelNoCS](#threadmodelnocs)|クラスを参照[CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md)します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CComMultiThreadModel::Decrement](#decrement)|(静的)デクリメント スレッド セーフな方法で指定された変数の値。|  
|[CComMultiThreadModel::Increment](#increment)|(静的)スレッド セーフな方法で指定された変数の値をインクリメントします。|  
  
## <a name="remarks"></a>コメント  
 通常、使用して`CComMultiThreadModel`2 つのいずれかを通して`typedef`[CComObjectThreadModel] の名前 (atl typedefs.md #ccomobjectthreadmodel または [CComGlobalsThreadModel] (atl typedefs.md #ccomglobalsthreadmodel します。 各によって参照されるクラス`typedef`次の表に示すように使用すると、スレッド処理モデルによって異なります。  
  
|typedef|シングル スレッド|アパートメント スレッド|フリー スレッド|  
|-------------|----------------------|-------------------------|--------------------|  
|`CComObjectThreadModel`|S|S|M|  
|`CComGlobalsThreadModel`|S|M|M|  
  
 S= `CComSingleThreadModel`;M =`CComMultiThreadModel`  
  
 `CComMultiThreadModel`3 つの定義自体`typedef`名。 `AutoCriticalSection``CriticalSection`を取得し、クリティカル セクションの所有権を解放するためのメソッドを提供するクラスを参照します。 `ThreadModelNoCS`参照クラス [CComMultiThreadModelNoCS(ccommultithreadmodelnocs-class.md) します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atlbase.h  
  
##  <a name="autocriticalsection"></a>CComMultiThreadModel::AutoCriticalSection  
 使用する場合`CComMultiThreadModel`、`typedef`名`AutoCriticalSection`クラスを参照[CComAutoCriticalSection](ccomautocriticalsection-class.md)を取得し、クリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。  
  
```
typedef CComAutoCriticalSection AutoCriticalSection;
```  
  
### <a name="remarks"></a>コメント  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md)と[CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)もの定義を含む`AutoCriticalSection`します。 次の表は、スレッド処理モデル クラスとによって参照されるクリティカル セクション クラス間のリレーションシップを示しています`AutoCriticalSection`:。  
  
|定義されたクラス|参照されるクラス|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 他に、 `AutoCriticalSection`、使用することができます、`typedef`名[CriticalSection](#criticalsection)します。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは静的クラス メンバーの場合は、CRT のスタートアップ コードを削除します。  
  
### <a name="example"></a>例  
 次のコードがモデル[CComObjectRootEx](ccomobjectrootex-class.md)、および例示します`AutoCriticalSection`スレッド環境で使用されています。  
  

```cpp  
template<class ThreadModel>
class CMyAutoCritClass
{
public:
   typedef ThreadModel _ThreadModel;
   typedef typename _ThreadModel::AutoCriticalSection _CritSec;

   CMyAutoCritClass() : m_dwRef(0) {}

   ULONG InternalAddRef()
   {
      return _ThreadModel::Increment(&m_dwRef);
   }
   ULONG InternalRelease()
   {
      return _ThreadModel::Decrement(&m_dwRef);   
   }
   void Lock() { m_critsec.Lock( ); }
   void Unlock() { m_critsec.Unlock(); }

private:
   _CritSec m_critsec;
   LONG m_dwRef;
```  
  
 次の表の結果を表示する、`InternalAddRef`と`Lock`に応じてメソッド、**表**テンプレート パラメーターと、アプリケーションで使用されるスレッド モデル。  
  
### <a name="threadmodel--ccomobjectthreadmodel"></a>表 CComObjectThreadModel =  
  
|メソッド|1 つ以上のアパートメント スレッド|フリー スレッド|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|増分値は、スレッド セーフではありません。|増分値は、スレッド セーフです。|  
|`Lock`|何も実行します。クリティカル セクションをロックすることはありません。|クリティカル セクションがロックされています。|  
  
### <a name="threadmodel--ccomobjectthreadmodelthreadmodelnocs"></a>表 CComObjectThreadModel::ThreadModelNoCS =  
  
|メソッド|1 つ以上のアパートメント スレッド|フリー スレッド|  
|------------|-----------------------------------|--------------------|  
|`InternalAddRef`|増分値は、スレッド セーフではありません。|増分値は、スレッド セーフです。|  
|`Lock`|何も実行します。クリティカル セクションをロックすることはありません。|何も実行します。クリティカル セクションをロックすることはありません。|  
  
##  <a name="criticalsection"></a>CComMultiThreadModel::CriticalSection  
 使用する場合`CComMultiThreadModel`、`typedef`名`CriticalSection`クラスを参照[CComCriticalSection](ccomcriticalsection-class.md)を取得し、クリティカル セクション オブジェクトの所有権を解放するためのメソッドを提供します。  
  
```
typedef CComCriticalSection CriticalSection;
```  
  
### <a name="remarks"></a>コメント  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md)と[CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)もの定義を含む`CriticalSection`します。 次の表は、スレッド処理モデル クラスとによって参照されるクリティカル セクション クラス間のリレーションシップを示しています`CriticalSection`:。  
  
|定義されたクラス|参照されるクラス|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComCriticalSection`|  
|`CComSingleThreadModel`|`CComFakeCriticalSection`|  
|`CComMultiThreadModelNoCS`|`CComFakeCriticalSection`|  
  
 他に、 `CriticalSection`、使用することができます、`typedef`名[AutoCriticalSection](#autocriticalsection)します。 指定しないでください`AutoCriticalSection`グローバル オブジェクトまたは静的クラス メンバーの場合は、CRT のスタートアップ コードを削除します。  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)します。  
  
##  <a name="decrement"></a>CComMultiThreadModel::Decrement  
 この静的関数は、Win32 関数を呼び出して[InterlockedDecrement](http://msdn.microsoft.com/library/windows/desktop/ms683580)、指す変数の値をデクリメント`p`します。  
  
```
static ULONG WINAPI Decrement(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]デクリメントする変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 減算の結果が 0 で、 `Decrement` 0 を返します。 減算の結果が&0; 以外の場合、戻り値は&0; 以外の値もですが、減算の結果が等しくない場合があります。  
  
### <a name="remarks"></a>コメント  
 **InterlockedDecrement**複数のスレッドが同時にこの変数を使用することを防止します。  
  
##  <a name="increment"></a>CComMultiThreadModel::Increment  
 この静的関数は、Win32 関数を呼び出して[InterlockedIncrement](http://msdn.microsoft.com/library/windows/desktop/ms683614)が指す変数の値をインクリメントする`p`です。  
  
```
static ULONG WINAPI Increment(LPLONG p) throw ();
```  
  
### <a name="parameters"></a>パラメーター  
 `p`  
 [in]インクリメントする変数へのポインター。  
  
### <a name="return-value"></a>戻り値  
 インクリメントの結果が 0、**インクリメント**0 を返します。 インクリメントの結果が&0; 以外の場合、戻り値は&0; 以外の値もですが、増分の結果が等しくない場合があります。  
  
### <a name="remarks"></a>コメント  
 **InterlockedIncrement**複数のスレッドが同時にこの変数を使用することを防止します。  
  
##  <a name="threadmodelnocs"></a>CComMultiThreadModel::ThreadModelNoCS  
 使用する場合`CComMultiThreadModel`、`typedef`名`ThreadModelNoCS`クラスを参照[CComMultiThreadModelNoCS](ccommultithreadmodelnocs-class.md)します。  
  
```
typedef CComMultiThreadModelNoCS ThreadModelNoCS;
```  
  
### <a name="remarks"></a>コメント  
 `CComMultiThreadModelNoCS`インクリメントおよびデクリメント変数のスレッド セーフであるメソッドを提供します。ただし、クリティカル セクションは行いません。  
  
 [CComSingleThreadModel](ccomsinglethreadmodel-class.md)と`CComMultiThreadModelNoCS`もの定義を含む`ThreadModelNoCS`します。 次の表は、スレッド処理モデル クラスとによって参照されるクラス間のリレーションシップを示しています`ThreadModelNoCS`:。  
  
|定義されたクラス|参照されるクラス|  
|----------------------|----------------------|  
|`CComMultiThreadModel`|`CComMultiThreadModelNoCS`|  
|`CComSingleThreadModel`|`CComSingleThreadModel`|  
|`CComMultiThreadModelNoCS`|`CComMultiThreadModelNoCS`|  
  
### <a name="example"></a>例  
 参照してください[CComMultiThreadModel::AutoCriticalSection](#autocriticalsection)します。  
  
## <a name="see-also"></a>関連項目  
 [CComSingleThreadModel クラス](ccomsinglethreadmodel-class.md)   
 [CComAutoCriticalSection クラス](ccomautocriticalsection-class.md)   
 [CComCriticalSection クラス](ccomcriticalsection-class.md)   
 [クラスの概要](../atl-class-overview.md)

