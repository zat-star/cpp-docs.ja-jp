---
title: "CSingleLock クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSingleLock
dev_langs:
- C++
helpviewer_keywords:
- CSingleLock class
- threading [MFC], access control
- synchronization objects, access control
- threading [MFC], synchronization
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
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
ms.openlocfilehash: b1efc2daf1c3714446223cc69f9cc2a6a3401173
ms.lasthandoff: 02/24/2017

---
# <a name="csinglelock-class"></a>CSingleLock クラス
マルチスレッド プログラムで&1; つのリソースのアクセス制御に使うアクセス コントロール機構を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSingleLock  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSingleLock::CSingleLock](#csinglelock)|`CSingleLock` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSingleLock::IsLocked](#islocked)|オブジェクトがロックされているかどうかを判断します。|  
|[CSingleLock::Lock](#lock)|同期オブジェクトを待機します。|  
|[CSingleLock::Unlock](#unlock)|同期オブジェクトを解放します。|  
  
## <a name="remarks"></a>コメント  
 `CSingleLock`基本クラスはありません。  
  
 同期クラスを使用するために[CSemaphore](../../mfc/reference/csemaphore-class.md)、 [CMutex](../../mfc/reference/cmutex-class.md)、 [CCriticalSection](../../mfc/reference/ccriticalsection-class.md)、および[CEvent](../../mfc/reference/cevent-class.md)、どちらかを作成する必要があります、`CSingleLock`または[CMultiLock](../../mfc/reference/cmultilock-class.md)オブジェクトを待機し、同期オブジェクトを解放します。 使用`CSingleLock`のみ必要がある場合、一度に&1; つのオブジェクト上で待機します。 使用して**CMultiLock**特定の時刻に使用できる複数のオブジェクトがある場合。  
  
 使用する、`CSingleLock`オブジェクト、被制御リソースのクラスのメンバー関数内部のコンス トラクターを呼び出します。 まず、 [IsLocked](#islocked)メンバー関数が使用可能なリソースを判断します。 である場合は、メンバー関数の残りの部分を続行します。 リソースが使用できない場合は、一定のリソースが解放されるまでの時間を待つか、エラーが返されます。 リソースの使用が完了したらを呼び出すか、[ロックの解除](#unlock)関数の場合、`CSingleLock`オブジェクトを使用して再度、または許可する、`CSingleLock`オブジェクトを破棄します。  
  
 `CSingleLock`オブジェクトから派生したオブジェクトの存在を必要と[関数](../../mfc/reference/csyncobject-class.md)します。 これは、通常、被制御リソースのクラスのデータ メンバーです。 使用する方法の詳細についての`CSingleLock`オブジェクト、記事を参照して[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CSingleLock`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmt.h  
  
##  <a name="a-namecsinglelocka--csinglelockcsinglelock"></a><a name="csinglelock"></a>CSingleLock::CSingleLock  
 `CSingleLock` オブジェクトを構築します。  
  
```  
explicit CSingleLock(
    CSyncObject* pObject,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>パラメーター  
 `pObject`  
 同期オブジェクトにアクセスできるへのポインター。 ことはできません**NULL**します。  
  
 `bInitialLock`  
 最初に指定されたオブジェクトにアクセスしようとするかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 この関数は、被制御リソースのアクセスのメンバー関数内で通常から呼び出されます。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities&#19;](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]  
  
##  <a name="a-nameislockeda--csinglelockislocked"></a><a name="islocked"></a>CSingleLock::IsLocked  
 オブジェクトに関連付けられているかどうかを判断、`CSingleLock`オブジェクトが非シグナル状態 (利用不可)。  
  
```  
BOOL IsLocked();
```  
  
### <a name="return-value"></a>戻り値  
 オブジェクトがロックされている場合は 0 以外それ以外の場合 0 を返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities&#20;](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]  
  
##  <a name="a-namelocka--csinglelocklock"></a><a name="lock"></a>CSingleLock::Lock  
 この関数に渡される同期オブジェクトによって制御されるリソースにアクセスするために、`CSingleLock`コンス トラクターです。  
  
```  
BOOL Lock(DWORD dwTimeOut = INFINITE);
```  
  
### <a name="parameters"></a>パラメーター  
 *dwTimeOut*  
 同期オブジェクトを使用できるまで待機する時間を指定 (シグナル状態になる)。 場合**無限**、`Lock`を返す前に、オブジェクトがシグナル状態になるまで待機します。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 同期オブジェクトがシグナル状態になる場合`Lock`が正常に返され、スレッドは、オブジェクトを所有します。 同期オブジェクトが非シグナル状態の場合 (利用不可)、`Lock`同期オブジェクトで指定されたミリ秒数までシグナル状態になるを待機は、 *dwTimeOut*パラメーター。 同期オブジェクトが指定された時間内シグナル状態になるいないしなかった場合`Lock`エラーを返します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities #&21;](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
##  <a name="a-nameunlocka--csinglelockunlock"></a><a name="unlock"></a>CSingleLock::Unlock  
 所有する同期オブジェクトを解放`CSingleLock`します。  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `lCount`  
 リリースへのアクセスの数。 1 以上であることが必要です。 指定の量を最大値を超えるオブジェクトの数となる場合、カウントは変更されず、関数を返します**FALSE**します。  
  
 `lPrevCount`  
 同期オブジェクトの前のカウントを受け取るように変数を指します。 場合**NULL**、前のカウントは返されません。  
  
### <a name="return-value"></a>戻り値  
 関数が成功した場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 この関数は`CSingleLock`のデストラクターです。  
  
 セマフォのアクセスの&2; つ以上のカウントを解放する必要がある場合は、2 番目の形式を使用して`Unlock`リリースへのアクセス数を指定します。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities #&21;](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
## <a name="see-also"></a>関連項目  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMultiLock クラス](../../mfc/reference/cmultilock-class.md)

