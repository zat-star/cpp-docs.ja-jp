---
title: "CSemaphore クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 811510bab51ab7909b90b52247d34b71dda5b961
ms.contentlocale: ja-jp
ms.lasthandoff: 04/04/2017

---
# <a name="csemaphore-class"></a>CSemaphore クラス
クラスのオブジェクト`CSemaphore`「セマフォ」を表す — 現在指定されたリソースにアクセスするスレッドの数のカウントにアクセスを管理する 1 つまたは複数のプロセスで、限られた数のスレッドを許可する同期オブジェクトです。  
  
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
 セマフォは、ユーザー数に制限をサポートできるだけ共有リソースへのアクセス制御に役立ちます。 現在のカウント、`CSemaphore`オブジェクトは許可されているその他のユーザーの数。 によって制御されるリソースを使用する試みがすべて、カウントが 0 になったときに、 **CSemaphore**カウントが 0 またはオブジェクトがシステムのキューに挿入され、タイムアウトまで待機します。 構築中に同時に、被制御リソースにアクセスできるユーザーの最大数が指定されて、`CSemaphore`オブジェクト。  
  
 使用する、 **CSemaphore**オブジェクトを構築、`CSemaphore`オブジェクトが必要なとき。 、を待機する、セマフォの名前を指定し、アプリケーションで最初に所有する必要があります。 コンス トラクターは、制御が戻るとき、セマフォにアクセスできます。 呼び出す[したら](../../mfc/reference/csyncobject-class.md#unlock)を完了すると被制御リソースにアクセスします。  
  
 使用する代替方法`CSemaphore`オブジェクトは、型の変数を追加する`CSemaphore`を制御したいクラスのデータ メンバーとして。 コンス トラクターの呼び出し、制御されるオブジェクトの構築時に、`CSemaphore`初期を指定するデータ メンバーがアクセス数、最大のアクセス数、(場合に、プロセス境界を越えて使用されます)、セマフォの名前および必要なセキュリティの属性です。  
  
 によって制御されるリソースにアクセスする`CSemaphore`オブジェクトがこの方法では、いずれかの型の変数をまず作成[CSingleLock](../../mfc/reference/csinglelock-class.md)または型[CMultiLock](../../mfc/reference/cmultilock-class.md)リソースのアクセス メンバー関数。 まず、ロック オブジェクトの`Lock`メンバー関数 (たとえば、 [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock))。 この時点では、スレッドはいずれか、リソースにアクセスをお待ちのリソースを解放して、アクセスを取得またはリソースが解放されるまで、リソースにアクセスするために失敗して、タイムアウトまで待機します。 いずれの場合、リソース アクセスがスレッド セーフな方法です。 リソースを解放するには、ロック オブジェクトの`Unlock`メンバー関数 (たとえば、 [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock))、またはスコープから除外するロック オブジェクトを許可します。  
  
 また、作成することができます、 **CSemaphore** 、スタンドアロン オブジェクトし、被制御リソースにアクセスする前に明示的にアクセスします。 ソース コードを読む人にはわかり中に、このメソッドは、エラーが発生しやすいです。  
  
 使用する方法の詳細についての**CSemaphore** 、オブジェクトが、記事を参照して[マルチ スレッド: 同期クラスを使用する方法](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [関数](../../mfc/reference/csyncobject-class.md)  
  
 `CSemaphore`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxmt.h  
  
##  <a name="csemaphore"></a>CSemaphore::CSemaphore  
 名前付きまたは名前のない構築`CSemaphore`オブジェクト。  
  
```  
CSemaphore(
    LONG lInitialCount = 1,  
    LONG lMaxCount = 1,  
    LPCTSTR pstrName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```  
  
### <a name="parameters"></a>パラメーター  
 *lInitialCount*  
 セマフォの初期の使用状況カウントします。 0 以上にする必要がありますに等しいまたはそれよりも小さいと`lMaxCount`です。  
  
 `lMaxCount`  
 セマフォの最大使用率カウントします。 1 以上であることが必要です。  
  
 `pstrName`  
 セマフォの名前。 プロセスの境界を越えて、セマフォにアクセスする場合を指定する必要があります。 場合`NULL`オブジェクトは名前付きできません。 コンス トラクターは、ビルド、新しい名前には、既存のセマフォが一致すると、`CSemaphore`その名前のセマフォを参照するオブジェクト。 名前には、セマフォではない既存の同期オブジェクトが一致すると、構築が失敗します。  
  
 *lpsaAttributes*  
 セマフォ オブジェクトのセキュリティ属性。 この構造体の詳細を参照してください。 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)で、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]です。  
  
### <a name="remarks"></a>コメント  
 アクセスまたはリリース、`CSemaphore`オブジェクトを作成、 [CMultiLock](../../mfc/reference/cmultilock-class.md)または[CSingleLock](../../mfc/reference/csinglelock-class.md)オブジェクトと呼び出しの[ロック](../../mfc/reference/csinglelock-class.md#lock)と[Unlock](../../mfc/reference/csinglelock-class.md#unlock)メンバー関数。  
  
> [!IMPORTANT]
>  作成した後、`CSemaphore`オブジェクトを使用して[GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360)をミュー テックスが既に存在しないことを確認します。 ミュー テックスが予期せず存在、悪意のあるプロセスが発生したり、悪意ミュー テックスを使用することがある必ずしも意図している可能性があります。 ここでは、推奨されるセキュリティを考慮したプロシージャがハンドルを終了し、クリックすると、オブジェクトの作成でエラーが発生しました。  
  
## <a name="see-also"></a>関連項目  
 [関数クラス](../../mfc/reference/csyncobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)




