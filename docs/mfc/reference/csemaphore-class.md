---
title: "CSemaphore クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSemaphore
- AFXMT/CSemaphore
- AFXMT/CSemaphore::CSemaphore
dev_langs:
- C++
helpviewer_keywords:
- synchronization objects, semaphores
- CSemaphore class
- semaphores
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
caps.latest.revision: 23
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
ms.openlocfilehash: 31de1e553ea2facea6b70c284aecdbf10e22c89f
ms.lasthandoff: 02/24/2017

---
# <a name="csemaphore-class"></a>CSemaphore クラス
クラスのオブジェクト`CSemaphore`「セマフォ」を表す、現在、指定したリソースにアクセスするスレッドの数のカウントにアクセスを管理する&1; つまたは複数のプロセスのスレッド数に制限をできるようにする同期オブジェクトです。  
  
## <a name="syntax"></a>構文  
  
```  
class CSemaphore : public CSyncObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSemaphore::CSemaphore](#csemaphore)|`CSemaphore` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 セマフォは、ユーザー数に制限をサポートできるだけ、共有リソースへのアクセス制御に役立ちます。 現在の数、`CSemaphore`オブジェクトは、許可された他のユーザーの数。 制御されるリソースを使用する試みがすべて、カウントが 0 になったときに、 **CSemaphore**カウントが 0 またはオブジェクトがシステム キューに挿入され、タイムアウトまで待機します。 被制御リソースに同時にアクセスできるユーザーの最大数が構築するときに指定されている、`CSemaphore`オブジェクトです。  
  
 使用する、 **CSemaphore**オブジェクト、構築、`CSemaphore`オブジェクトが必要な場合です。 待機するセマフォの名前を指定し、アプリケーションを所有して最初にします。 セマフォは、コンス トラクターは、制御が戻るとき、アクセスできます。 呼び出す[したら](../../mfc/reference/csyncobject-class.md#unlock)が終了したら、被制御リソースにアクセスします。  
  
 別の方法を使用するため`CSemaphore`オブジェクト型の変数を追加する方法です`CSemaphore`コントロールするクラスにデータ メンバーとして参加します。 コンス トラクターを呼び出す、制御されるオブジェクトの構築時に、`CSemaphore`初期を指定するデータ メンバーがアクセス回数、最大アクセス数、(これは、プロセス境界で使用されます) 場合、セマフォの名前および必要なセキュリティ属性。  
  
 によって制御されるリソースにアクセスする`CSemaphore`この方法でオブジェクトが最初にいずれかの型の変数を作成[CSingleLock](../../mfc/reference/csinglelock-class.md)または型[CMultiLock](../../mfc/reference/cmultilock-class.md)リソースのアクセスのメンバー関数。 まず、ロック オブジェクトの`Lock`メンバー関数 (たとえば、 [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock))。 この時点で、スレッドは、リソースにアクセスできる待つ必要がリソースを解放して、アクセスを取得またはリソースにアクセスするために失敗しているタイムアウトとリソースが解放されるまでの待機に。 いずれの場合、リソースは、スレッド セーフな方法でアクセスがあった。 リソースを解放するには、ロック オブジェクトを使用して`Unlock`メンバー関数 (たとえば、 [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock))、またはスコープ外に収まるように、ロック オブジェクトを許可します。  
  
 または、作成、 **CSemaphore** 、スタンドアロン オブジェクトし、被制御リソースにアクセスする前に明示的にアクセスします。 この方法は、ソース コードを読む人にはわかりは、エラーが発生しやすくします。  
  
 使用する方法の詳細についての**CSemaphore**オブジェクト、記事を参照して[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [関数](../../mfc/reference/csyncobject-class.md)  
  
 `CSemaphore`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmt.h  
  
##  <a name="csemaphore"></a>CSemaphore::CSemaphore  
 名前付き、または名前を作成`CSemaphore`オブジェクトです。  
  
```  
CSemaphore(
    LONG lInitialCount = 1,  
    LONG lMaxCount = 1,  
    LPCTSTR pstrName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lInitialCount*  
 セマフォの初期の使用率カウントします。 0 以上にする必要があり、以下に`lMaxCount`します。  
  
 `lMaxCount`  
 セマフォの最大使用率カウントします。 1 以上であることが必要です。  
  
 `pstrName`  
 セマフォの名前。 プロセス境界をまたいでセマフォがアクセスされる場合を指定する必要があります。 場合`NULL,`オブジェクトの名前付きが解除されます。 コンス トラクターは、ビルド、新しい名前には、既存のセマフォが一致すると、`CSemaphore`その名前のセマフォを参照するオブジェクト。 名前には、セマフォではない既存の同期オブジェクトが一致すると、構築が失敗します。  
  
 *lpsaAttributes*  
 セマフォ オブジェクトのセキュリティ属性。 この構造体の詳細については、次を参照してください。 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 アクセスまたはリリース、`CSemaphore`オブジェクトは、作成、 [CMultiLock](../../mfc/reference/cmultilock-class.md)または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトと呼び出しの[ロック](../../mfc/reference/csinglelock-class.md#lock)と[Unlock](../../mfc/reference/csinglelock-class.md#unlock)メンバー関数。  
  
> [!IMPORTANT]
>  作成した後、`CSemaphore`オブジェクトを使用[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)ミュー テックスがまだ存在しないことを確認します。 ミュー テックスが予期せず存在して問題のあるプロセスが発生したり、悪意を持って、ミュー テックスを使用するつもりが可能性があります。 この場合は、セキュリティ意識の推奨手順は、ハンドルを閉じるし、クリックすると、エラーが発生しました、オブジェクトを作成するにです。  
  
## <a name="see-also"></a>関連項目  
 [関数のクラス](../../mfc/reference/csyncobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




