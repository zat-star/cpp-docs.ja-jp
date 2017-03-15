---
title: "CMutex クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Mutex
- CMutex
dev_langs:
- C++
helpviewer_keywords:
- CMutex class
- synchronization classes, CMutex class
- synchronization objects, mutex
- mutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
caps.latest.revision: 22
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
ms.openlocfilehash: 159f2e02dfe44d74ebcaad687a23cef734b61fc9
ms.lasthandoff: 02/24/2017

---
# <a name="cmutex-class"></a>CMutex クラス
「ミュー テックス」を表す、リソースへの&1; つのスレッド相互に排他的なアクセスを許可する同期オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
class CMutex : public CSyncObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CMutex::CMutex](#cmutex)|`CMutex` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 ミュー テックスは、一度に&1; つのスレッドも、データまたはその他の制御されたリソースを変更することがある場合に便利です。 たとえば、リンク リストにノードを追加するは、一度に&1; つのスレッドでのみ許可するプロセスです。 使用して、`CMutex`だけで、一覧に、一度に&1; つのスレッドがアクセスできるリンクのリストを制御するオブジェクト。  
  
 使用する、`CMutex`オブジェクト、構築、`CMutex`オブジェクトが必要な場合です。 待機するミュー テックスの名前を指定し、アプリケーションで最初に所有する必要があります。 コンス トラクターは、制御が戻るとき、ミュー テックスをアクセスできます。 呼び出す[したら](../../mfc/reference/csyncobject-class.md#unlock)が終了したら、被制御リソースにアクセスします。  
  
 別の方法を使用するため`CMutex`オブジェクト型の変数を追加する方法です`CMutex`コントロールするクラスにデータ メンバーとして参加します。 コンス トラクターを呼び出す、制御されるオブジェクトの構築時に、`CMutex`データ メンバーが、ミュー テックスが最初に所有する、ミュー テックスの名前 (場合に、プロセスの境界を越えて使用されます)、およびセキュリティ属性を必要なかどうかを指定します。  
  
 によって制御されるリソースにアクセスする`CMutex`この方法でオブジェクトが最初にいずれかの型の変数を作成[CSingleLock](../../mfc/reference/csinglelock-class.md)または型[CMultiLock](../../mfc/reference/cmultilock-class.md)リソースのアクセスのメンバー関数。 まず、ロック オブジェクトの`Lock`メンバー関数 (たとえば、 [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock))。 この時点で、スレッドは、リソースにアクセスできる待つ必要がリソースを解放して、アクセスを取得またはリソースにアクセスするために失敗しているタイムアウトとリソースが解放されるまでの待機に。 いずれの場合、リソースは、スレッド セーフな方法でアクセスがあった。 リソースを解放するには、ロック オブジェクトを使用して`Unlock`メンバー関数 (たとえば、 [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock))、またはスコープ外に収まるように、ロック オブジェクトを許可します。  
  
 使用する方法について`CMutex`オブジェクト、記事を参照して[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [関数](../../mfc/reference/csyncobject-class.md)  
  
 `CMutex`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmt.h  
  
##  <a name="a-namecmutexa--cmutexcmutex"></a><a name="cmutex"></a>CMutex::CMutex  
 名前付き、または名前を作成`CMutex`オブジェクトです。  
  
```  
CMutex(
    BOOL bInitiallyOwn = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 `bInitiallyOwn`  
 場合に指定のスレッドの作成、`CMutex`オブジェクトでは、ミュー テックスによって制御されているリソースへのアクセスは最初にします。  
  
 `lpszName`  
 `CMutex` オブジェクトの名前。 同じ名前の別のミュー テックスが存在する場合、`lpszName`プロセス境界をまたいでオブジェクトを使用する場合に指定する必要があります。 場合**NULL**、ミュー テックスの名前付きが解除されます。 コンス トラクターは、ビルド、新しい名前には、既存のミュー テックスが一致すると、`CMutex`その名前のミュー テックスを参照するオブジェクト。 名前には、ミュー テックスではない既存の同期オブジェクトが一致すると、構築が失敗します。  
  
 `lpsaAttribute`  
 ミュー テックス オブジェクトのセキュリティ属性。 この構造体の詳細については、次を参照してください。 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 アクセスまたはリリース、`CMutex`オブジェクトは、作成、 [CMultiLock](../../mfc/reference/cmultilock-class.md)または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトと呼び出しの[ロック](../../mfc/reference/csinglelock-class.md#lock)と[Unlock](../../mfc/reference/csinglelock-class.md#unlock)メンバー関数。 場合、`CMutex`を呼び出すオブジェクトはスタンドアロンに使用されている必要がその`Unlock`メンバー関数をそれを解放します。  
  
> [!IMPORTANT]
>  作成した後、`CMutex`オブジェクトを使用[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)ミュー テックスがまだ存在しないことを確認します。 ミュー テックスが予期せず存在して問題のあるプロセスが発生したり、悪意を持って、ミュー テックスを使用するつもりが可能性があります。 この場合は、セキュリティ意識の推奨手順は、ハンドルを閉じるし、クリックすると、エラーが発生しました、オブジェクトを作成するにです。  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/csyncobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




