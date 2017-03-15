---
title: "CCriticalSection クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- synchronization objects, critical section
- CCriticalSection class
- critical sections
- synchronization classes, CCriticalSection class
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 25d4b124d089441503e9cb457e648695fc54660d
ms.lasthandoff: 02/24/2017

---
# <a name="ccriticalsection-class"></a>CCriticalSection クラス
「クリティカル セクション」を表す-リソースまたはコードのセクションにアクセスする時に&1; つのスレッドをできるようにする同期オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
class CCriticalSection : public CSyncObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CCriticalSection::CCriticalSection](#ccriticalsection)|`CCriticalSection` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CCriticalSection::Lock](#lock)|アクセスするために使用して、`CCriticalSection`オブジェクトです。|  
|[CCriticalSection::Unlock](#unlock)|`CCriticalSection` のオブジェクトを解放します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|内部へのポインターを取得**CRITICAL_SECTION**オブジェクトです。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CCriticalSection::m_sect](#m_sect)|A **CRITICAL_SECTION**オブジェクトです。|  
  
## <a name="remarks"></a>コメント  
 重要なセクションは、一度に&1; つのスレッドも、データまたはその他の制御されたリソースを変更することがある場合に便利です。 たとえば、リンク リストにノードを追加するは、一度に&1; つのスレッドでのみ許可するプロセスです。 使用して、`CCriticalSection`だけで、一覧に、一度に&1; つのスレッドがアクセスできるリンクのリストを制御するオブジェクト。  
  
> [!NOTE]
>  機能、`CCriticalSection`クラスが実際の Win32 によって提供される**CRITICAL_SECTION**オブジェクトです。  
  
 クリティカル セクションがミュー テックスの代わりに使用されます (を参照してください[CMutex](../../mfc/reference/cmutex-class.md)) と速度が重要なプロセス境界をまたいでリソースは使用されません。  
  
 2 つのメソッドを使用するため、`CCriticalSection`オブジェクト: スタンドアロンおよび埋め込みクラスにします。  
  
-   スタンドアロンを使用するスタンドアロン メソッド`CCriticalSection`オブジェクト、構築、`CCriticalSection`オブジェクトが必要な場合です。 呼び出してオブジェクトを明示的にコンス トラクターから正常に返された後にロック[ロック](#lock)します。 呼び出す[Unlock](#unlock)が終了したら、クリティカル セクションにアクセスします。 この方法は、ソース コードを読む人にはわかりはロックし、アクセスの前後にクリティカル セクションのロックを解除することが、エラーが発生しやすくします。  
  
     表示に適した方法は、使用する、 [CSingleLock](../../mfc/reference/csinglelock-class.md)クラスです。 `Lock`と`Unlock`メソッドは、例外が発生した場合、リソースのロック解除について心配する必要ありません。  
  
-   メソッドを追加することで、複数のスレッドでクラスを共有することもできますが埋め込まれている、 `CCriticalSection`-型データ メンバーをクラスと必要なときに、データ メンバーをロックします。  
  
 使用する方法について`CCriticalSection`オブジェクト、記事を参照して[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [関数](../../mfc/reference/csyncobject-class.md)  
  
 `CCriticalSection`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmt.h  
  
##  <a name="a-nameccriticalsectiona--ccriticalsectionccriticalsection"></a><a name="ccriticalsection"></a>CCriticalSection::CCriticalSection  
 `CCriticalSection` オブジェクトを構築します。  
  
```  
CCriticalSection();
```  
  
### <a name="remarks"></a>コメント  
 アクセスまたはリリース、`CCriticalSection`オブジェクトは、作成、 [CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトと呼び出しの[ロック](../../mfc/reference/csinglelock-class.md#lock)と[Unlock](../../mfc/reference/csinglelock-class.md#unlock)メンバー関数。 場合、`CCriticalSection`を呼び出すオブジェクトはスタンドアロンに使用されている必要がその[Unlock](#unlock)解放するメンバー関数。  
  
 コンス トラクターが必要なシステム メモリ、メモリ不足の例外の割り当てに失敗するかどうか (型の[関数](../../mfc/reference/cmemoryexception-class.md)) が自動的にスローされます。  
  
### <a name="example"></a>例  
  例を参照してください[CCriticalSection::Lock](#lock)します。  
  
##  <a name="a-namelocka--ccriticalsectionlock"></a><a name="lock"></a>CCriticalSection::Lock  
 クリティカル セクション オブジェクトにアクセスするには、このメンバー関数を呼び出します。  
  
```  
BOOL Lock();  
BOOL Lock(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>パラメーター  
 `dwTimeout`  
 `Lock`このパラメーターの値を無視します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 `Lock`クリティカル セクション オブジェクトがシグナル状態になるまでは返されませんブロッキング呼び出し (できるようになります)。  
  
 時間指定の待機が必要な場合は、行うこともできます、 [CMutex](../../mfc/reference/cmutex-class.md)オブジェクトの代わりに、`CCriticalSection`オブジェクトです。  
  
 場合`Lock`、メモリ不足の例外のために必要なシステム メモリを割り当てに失敗した (型の[関数](../../mfc/reference/cmemoryexception-class.md)) が自動的にスローされます。  
  
### <a name="example"></a>例  
 この例では、共有リソースへのアクセスを制御することで、入れ子になったクリティカル セクションの方法を示します (静的`_strShared`オブジェクト)、共有を使用して`CCriticalSection`オブジェクトです。 `SomeMethod`関数では、安全な方法での共有リソースの更新について説明します。  
  
 [!code-cpp[NVC_MFC_Utilities&#11;](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]  
  
##  <a name="a-namemsecta--ccriticalsectionmsect"></a><a name="m_sect"></a>CCriticalSection::m_sect  
 クリティカル セクション オブジェクトすべてで使用を含む`CCriticalSection`メソッドです。  
  
```  
CRITICAL_SECTION m_sect;  
```  
  
##  <a name="a-nameoperatorcriticalsectionstara--ccriticalsectionoperator-criticalsection"></a><a name="operator_critical_section_star"></a>CCriticalSection::operator CRITICAL_SECTION *  
 取得、 **CRITICAL_SECTION**オブジェクトです。  
  
```  
operator CRITICAL_SECTION*();
```   
  
### <a name="remarks"></a>コメント  
 内部へのポインターを取得するには、この関数を呼び出す**CRITICAL_SECTION**オブジェクトです。  
  
##  <a name="a-nameunlocka--ccriticalsectionunlock"></a><a name="unlock"></a>CCriticalSection::Unlock  
 リリース、`CCriticalSection`別のスレッドで使用するオブジェクト。  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>戻り値  
 0 以外の値、`CCriticalSection`オブジェクトがスレッドによって所有されているし、リリースが成功した。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 場合、`CCriticalSection`が使用されているスタンドアロン、`Unlock`クリティカル セクションによって制御されているリソースの使用の完了後すぐに呼び出す必要があります。 場合、 [CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトが使用されている`CCriticalSection::Unlock`ロック オブジェクトのにより呼び出される`Unlock`メンバー関数。  
  
### <a name="example"></a>例  
  例を参照してください[CCriticalSection::Lock](#lock)します。  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/csyncobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMutex クラス](../../mfc/reference/cmutex-class.md)

