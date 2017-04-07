---
title: "CEvent クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CEvent
- AFXMT/CEvent
- AFXMT/CEvent::CEvent
- AFXMT/CEvent::PulseEvent
- AFXMT/CEvent::ResetEvent
- AFXMT/CEvent::SetEvent
- AFXMT/CEvent::Unlock
dev_langs:
- C++
helpviewer_keywords:
- synchronization objects, event
- synchronization classes, CEvent class
- CEvent class
ms.assetid: df676042-ce27-4702-800a-e73ff4f44395
caps.latest.revision: 27
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 9edadeec87cf04ae6166c173c65463d1509eb1d8
ms.lasthandoff: 02/24/2017

---
# <a name="cevent-class"></a>CEvent クラス
別のイベントが発生したことを通知する&1; つのスレッドを有効にする同期オブジェクトであるイベントを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CEvent : public CSyncObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CEvent::CEvent](#cevent)|`CEvent` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CEvent::PulseEvent](#pulseevent)|セットは使用可能なイベント (シグナル状態になる)、待機中のスレッドを解放し、使用できなくするイベントを (非シグナル) に設定します。|  
|[CEvent::ResetEvent](#resetevent)|(非シグナル) を使用できないイベントを設定します。|  
|[CEvent::SetEvent](#setevent)|(シグナル) を使用可能なイベントを設定し、待機中のスレッドを解放します。|  
|[CEvent::Unlock](#unlock)|イベント オブジェクトを解放します。|  
  
## <a name="remarks"></a>コメント  
 イベントは、スレッドがそのタスクを実行するタイミングを知る必要があるときに便利です。 たとえば、データ アーカイブにデータをコピーするスレッドは、新しいデータを利用可能な場合に通知する必要があります。 使用して、`CEvent`オブジェクトに新しいデータがある場合は、コピー スレッドを通知する、スレッドがそのタスクをできるだけ早く行うことができます。  
  
 `CEvent`オブジェクトが&2; 種類あります。 手動および自動です。  
  
 自動`CEvent`には、少なくとも&1; つのスレッドが解放された後、このオブジェクトは、自動的に非シグナル状態 (利用不可) の状態を返します。 既定では、`CEvent`しない限り、オブジェクトが自動`TRUE`の`bManualReset`の構築時にパラメーター。  
  
 手動`CEvent`オブジェクトで設定された状態に保持[SetEvent](#setevent)または[ResetEvent](#resetevent)他の関数が呼び出されるまでです。 手動で作成する`CEvent`オブジェクトを渡す`TRUE`の`bManualReset`の構築時にパラメーター。  
  
 使用する、`CEvent`オブジェクト、構築、`CEvent`オブジェクトが必要な場合です。 待機し、アプリケーションが最初に所有しているを指定するイベントの名前を指定します。 コンス トラクターから戻るときに、イベントを表示できます。 呼び出す[SetEvent](#setevent)信号 (可能化すること) にイベント オブジェクトと、呼び出し[Unlock](#unlock)したら被制御リソースにアクセスします。  
  
 別の方法を使用するため`CEvent`オブジェクトは、型の変数を追加する`CEvent`を制御クラスにデータ メンバーとして参加します。 コンス トラクターを呼び出す、制御されるオブジェクトの構築時に、`CEvent`データ メンバーおよびイベントが最初に通知するかどうか、およびイベント オブジェクトが、(これは、プロセス境界で使用されます) 場合、イベントの名前の型を指定し、セキュリティの属性します。  
  
 制御されるリソースにアクセスする、`CEvent`オブジェクトのこの方法では、まずいずれかの型の変数を作成[CSingleLock](../../mfc/reference/csinglelock-class.md)または型[CMultiLock](../../mfc/reference/cmultilock-class.md)リソースのアクセス方法にします。 まず、`Lock`ロック オブジェクトのメソッド (たとえば、 [CMultiLock::Lock](../../mfc/reference/cmultilock-class.md#lock))。 この時点で、スレッドがいずれかにアクセス リソース、リソースを解放して、アクセスを取得またはリソースが解放されるまでの待機に待機、タイムアウトが発生しリソースにアクセスするために失敗します。 いずれの場合、リソースは、スレッド セーフな方法でアクセスがあった。 リソースを解放する呼び出し`SetEvent`イベント オブジェクトを通知し、使用する、`Unlock`ロック オブジェクトのメソッド (たとえば、 [CMultiLock::Unlock](../../mfc/reference/cmultilock-class.md#unlock))、させたり、ロック オブジェクトがスコープから除外します。  
  
 使用する方法の詳細についての`CEvent`オブジェクトを参照してください[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)します。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities #&45;](../../mfc/codesnippet/cpp/cevent-class_1.cpp)]  
  
 [!code-cpp[NVC_MFC_Utilities&#46;](../../mfc/codesnippet/cpp/cevent-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [関数](../../mfc/reference/csyncobject-class.md)  
  
 `CEvent`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmt.h  
  
##  <a name="cevent"></a>CEvent::CEvent  
 名前付き、または名前を作成`CEvent`オブジェクトです。  
  
```  
CEvent(
    BOOL bInitiallyOwn = FALSE,  
    BOOL bManualReset = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bInitiallyOwn`  
 場合**TRUE**のスレッド、 **CMultilock**または`CSingleLock`オブジェクトが有効になっています。 それ以外の場合、リソースにアクセスするすべてのスレッドは待機する必要があります。  
  
 *bManualReset*  
 場合**TRUE**、イベント オブジェクトは、手動のイベントか、それ以外の場合、イベント オブジェクトは、自動のイベントを指定します。  
  
 `lpszName`  
 `CEvent` オブジェクトの名前。 プロセス境界をまたいでオブジェクトを使用する場合を指定する必要があります。 コンス トラクターは、ビルド、新しい名前には、既存のイベントが一致すると、`CEvent`その名前のイベントを参照するオブジェクト。 名前には、イベントではない既存の同期オブジェクトが一致すると、構築が失敗します。 場合**NULL**名前は null になります。  
  
 `lpsaAttribute`  
 イベント オブジェクトのセキュリティ属性。 この構造体の詳細については、次を参照してください。 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 アクセスまたはリリース、`CEvent`オブジェクトは、作成、 [CMultiLock](../../mfc/reference/cmultilock-class.md)または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトと呼び出しの[ロック](../../mfc/reference/csinglelock-class.md#lock)と[Unlock](../../mfc/reference/csinglelock-class.md#unlock)メンバー関数。  
  
 状態を変更する、`CEvent`シグナル状態にオブジェクト (スレッドがない待機する) を呼び出す[SetEvent](#setevent)または[PulseEvent](#pulseevent)します。 状態を設定する、`CEvent`非シグナル状態にオブジェクト (スレッド待つ必要があります)、呼び出す[ResetEvent](#resetevent)します。  
  
> [!IMPORTANT]
>  作成した後、`CEvent`オブジェクトを使用[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)をミュー テックスがまだ存在していないことを確認します。 ミュー テックスが予期せず存在して問題のあるプロセスが発生したり、悪意を持って、ミュー テックスを使用するつもりが可能性があります。 ここでは、セキュリティ意識の推奨手順が、ハンドルを閉じるし、クリックすると、オブジェクトの作成でエラーが発生しました。  
  
##  <a name="pulseevent"></a>CEvent::PulseEvent  
 (使用可能) イベントをシグナルの状態を設定の待機中のスレッドを解放し、非シグナル状態 (利用不可) に自動的にリセットします。  
  
```  
BOOL PulseEvent();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 イベントが手動の場合は、待機中のすべてのスレッドがリリースされる、イベントが非シグナル状態に設定されてと`PulseEvent`を返します。 イベントが自動の場合は、1 つのスレッドがリリースされたら、イベントが非シグナル状態に設定されてと`PulseEvent`を返します。  
  
 待機しているスレッドがないか、すぐに解放する`PulseEvent`するイベントの状態を非シグナル状態に設定し、返します。  
  
 `PulseEvent`基になる Win32 を使用して`PulseEvent`待機状態からカーネル モードの非同期プロシージャ コールによって一時的に削除できる関数です。 したがって、`PulseEvent`の信頼性が低いと、新しいアプリケーションでは使用しない必要があります。 詳細については、次を参照してください。、 [PulseEvent 関数](http://msdn.microsoft.com/library/windows/desktop/ms684914)します。  
  
##  <a name="resetevent"></a>CEvent::ResetEvent  
 設定するイベントの状態まで非シグナル状態に明示的にシグナル状態に設定、 [SetEvent](#setevent)メンバー関数。  
  
```  
BOOL ResetEvent();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 これにより、すべてのスレッドが待機するには、このイベントにアクセスしたいです。  
  
 このメンバー関数は、自動イベントでは使用されません。  
  
##  <a name="setevent"></a>CEvent::SetEvent  
 待機中のスレッドを解放するイベントをシグナルの状態を設定します。  
  
```  
BOOL SetEvent();
```  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。 それ以外の場合に 0 です。  
  
### <a name="remarks"></a>コメント  
 イベントをまでシグナル状態になりますが、イベントが手動の場合は、 [ResetEvent](#resetevent)が呼び出されます。 ここでは、複数のスレッドが解放できます。 イベントが自動の場合は、1 つのスレッドが解放されるまで、イベントがシグナル状態残ります。 システムは、非シグナル状態イベントの状態が設定されます。 待機しているスレッドがない場合、状態は、1 つのスレッドが解放されるまでシグナル状態のままです。  
  
##  <a name="unlock"></a>CEvent::Unlock  
 イベント オブジェクトを解放します。  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>戻り値  
 自動イベントをイベント オブジェクトと、イベント、スレッドが所有している場合は 0 以外にはそれ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 解放するが、終了後、ロック オブジェクトが再利用することがある場合の自動イベントを現在所有するスレッドによって呼び出されます。 ロック オブジェクトは、再利用することはありませんが場合、この関数は、ロック オブジェクトのデストラクターを呼び出せません。  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/csyncobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)


