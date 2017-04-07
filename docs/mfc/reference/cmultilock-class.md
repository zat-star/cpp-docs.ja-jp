---
title: "CMultiLock クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiLock
- AFXMT/CMultiLock
- AFXMT/CMultiLock::CMultiLock
- AFXMT/CMultiLock::IsLocked
- AFXMT/CMultiLock::Lock
- AFXMT/CMultiLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CMultiLock class
- synchronization objects, access control
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: a58d59d8e4d7a1c542dee80295dd8eef6c8be338
ms.lasthandoff: 02/24/2017

---
# <a name="cmultilock-class"></a>CMultiLock クラス
マルチスレッド プログラムで複数のリソースのアクセス制御に使うアクセス コントロール機構を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CMultiLock  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMultiLock::CMultiLock](#cmultilock)|`CMultiLock` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CMultiLock::IsLocked](#islocked)|配列内の特定の同期オブジェクトがロックされているかどうかを判断します。|  
|[CMultiLock::Lock](#lock)|同期オブジェクトの配列を待機します。|  
|[CMultiLock::Unlock](#unlock)|すべての所有する同期オブジェクトを解放します。|  
  
## <a name="remarks"></a>コメント  
 `CMultiLock`基本クラスはありません。  
  
 同期クラスを使用して[CSemaphore](../../mfc/reference/csemaphore-class.md)、 [CMutex](../../mfc/reference/cmutex-class.md)、および[CEvent](../../mfc/reference/cevent-class.md)、いずれかを作成することができます、 **CMultiLock**または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトを待機し、同期オブジェクトを解放します。 使用して**CMultiLock**特定の時刻に使用できる複数のオブジェクトがある場合。 使用`CSingleLock`のみ必要がある場合、一度に&1; つのオブジェクト上で待機します。  
  
 使用する、 **CMultiLock**オブジェクトは、最初待機する同期オブジェクトの配列を作成します。 次を呼び出す、 **CMultiLock**制御されるリソースのクラスのメンバー関数内のオブジェクトのコンス トラクターです。 まず、[ロック](#lock)リソースの可用性を確認するメンバー関数 (通知)。 1 つの場合は、メンバー関数の残りの部分を続行します。 リソースが使用できない場合は、一定のリソースが解放されるまでの時間待つか、エラーが返されます。 リソースの使用が完了したらを呼び出すか、[ロックの解除](#unlock)関数の場合、 **CMultiLock**オブジェクトを使用して再度、または許可する、 **CMultiLock**オブジェクトを破棄します。  
  
 **CMultiLock**オブジェクトは、スレッドの数が多いが最も役に立つ`CEvent`オブジェクトに対応できます。 すべてを含む配列を作成、`CEvent`ポインター、および呼び出し`Lock`します。 いずれかのイベントがシグナル状態になるまで待機するスレッドになります。  
  
 使用する方法の詳細についての**CMultiLock**オブジェクト、記事を参照して[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CMultiLock`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmt.h  
  
##  <a name="cmultilock"></a>CMultiLock::CMultiLock  
 構築、 **CMultiLock**オブジェクトです。  
  
```  
CMultiLock(
    CSyncObject* ppObjects [ ],  
    DWORD dwCount,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `ppObjects`  
 待機する同期オブジェクトへのポインターの配列。 ことはできません**NULL**します。  
  
 `dwCount`  
 内のオブジェクト数`ppObjects`します。 1 以上であることが必要です。  
  
 `bInitialLock`  
 最初に指定されたオブジェクトのいずれかにアクセスしようとするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 この関数は待機する同期オブジェクトの配列を作成後に呼び出されます。 通常使用可能になる同期オブジェクトの&1; つを待機する必要がありますスレッド内から呼び出されます。  
  
##  <a name="islocked"></a>CMultiLock::IsLocked  
 指定したオブジェクトが非シグナル状態かどうかを (利用不可)。  
  
```  
BOOL IsLocked(DWORD dwItem);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwItem*  
 状態が照会されるオブジェクトに対応するオブジェクトの配列内のインデックス。  
  
### <a name="return-value"></a>戻り値  
 指定したオブジェクトがロックされている場合は 0 以外それ以外の場合 0 を返します。  
  
##  <a name="lock"></a>CMultiLock::Lock  
 この関数に渡された同期オブジェクトによって制御されているリソースにアクセスするために、 **CMultiLock**コンス トラクターです。  
  
```  
DWORD Lock(
    DWORD dwTimeOut = INFINITE,  
    BOOL bWaitForAll = TRUE,  
    DWORD dwWakeMask = 0);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwTimeOut*  
 同期オブジェクトを使用できるまで待機する時間を指定 (シグナル状態になる)。 場合**無限**、`Lock`を返す前に、オブジェクトがシグナル状態になるまで待機します。  
  
 `bWaitForAll`  
 返す前に、同時に待機しているすべてのオブジェクトをシグナル状態になる必要があるかどうかを指定します。 場合**FALSE**、`Lock`が、待機しているオブジェクトのいずれかが通知された場合に返されます。  
  
 `dwWakeMask`  
 待機を中止できるはその他の条件を指定します。 このパラメーターの使用可能なオプションの一覧については、次を参照してください。 [MsgWaitForMultipleObjects](http://msdn.microsoft.com/library/windows/desktop/ms684242)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="return-value"></a>戻り値  
 場合`Lock`失敗すると、以下の値を返します: 1。 成功した場合、次の値のいずれかを返します。  
  
-   間**WAIT_OBJECT_0**と**WAIT_OBJECT_0** + (– 1 のオブジェクトの数)  
  
     場合`bWaitForAll`は**TRUE**、すべてのオブジェクトがシグナル状態になる (使用可能)。 場合`bWaitForAll`は**FALSE**、戻り値 – **WAIT_OBJECT_0**が通知されるオブジェクトのオブジェクトの配列内のインデックスを (使用可能)。  
  
- **WAIT_OBJECT_0** + (オブジェクトの数)  
  
     指定されたイベント`dwWakeMask`は、スレッドの入力キューで使用できます。  
  
-   間**WAIT_ABANDONED_0**と**WAIT_ABANDONED_0** + (– 1 のオブジェクトの数)  
  
     場合`bWaitForAll`は**TRUE**、すべてのオブジェクトがシグナル状態になる、および、ミュー テックスの破棄されたオブジェクトは、少なくとも&1; つのオブジェクト。 場合`bWaitForAll`は**FALSE**、戻り値 – **WAIT_ABANDONED_0**待機を実行する破棄済みミュー テックス オブジェクトのオブジェクトの配列のインデックスします。  
  
- **正常に終了しました。**  
  
     指定されたタイムアウト間隔*dwTimeOut*待機に成功することがなく有効期限が切れています。  
  
### <a name="remarks"></a>コメント  
 場合`bWaitForAll`は**TRUE**、`Lock`は同時にすべての同期オブジェクトがシグナル状態になるとすぐに正常に復帰します。 場合`bWaitForAll`は**FALSE**、 `Lock`&1; つまたは複数の同期オブジェクトがシグナル状態にするとすぐに戻ります。  
  
 場合`Lock`で指定されたミリ秒数を超えないを待機する、すぐに返すことがない、 *dwTimeOut*パラメーターを返す前にします。 場合*dwTimeOut*は**無限**、`Lock`はオブジェクトへのアクセスが得られるか、条件で指定するまでは返されません`dwWakeMask`が満たされています。 それ以外の場合`Lock`が同期オブジェクトを取得できません、これは正常に復帰; いない場合は、エラーが返されます。  
  
##  <a name="unlock"></a>CMultiLock::Unlock  
 所有する同期オブジェクトを解放`CMultiLock`します。  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lCount`  
 参照の数をカウントを解放します。 1 以上であることが必要です。 指定の量を最大値を超えるオブジェクトの数となる場合、カウントは変更されず、関数を返します**FALSE**します。  
  
 `lPrevCount`  
 同期オブジェクトが、前のカウントを受け取るように変数を指します。 場合**NULL**、前のカウントは返されません。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は`CMultiLock`のデストラクターです。  
  
 最初のフォーム`Unlock`によって管理される同期オブジェクトのロックを解除しようとする`CMultiLock`です。 2 番目の形式の`Unlock`のロックを解除しようとする、`CSemaphore`が所有するオブジェクト`CMultiLock`します。 場合`CMultiLock`いずれかを所有していないロック`CSemaphore`関数から返されます**FALSE**、それ以外を返します**TRUE**します。 `lCount``lpPrevCount`のパラメーターと同じでは、まったく[CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)します。 2 番目の形式の`Unlock`は多重の状況に該当することはほとんどありません。  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)




