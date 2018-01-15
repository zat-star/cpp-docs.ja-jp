---
title: "IUMSThreadProxy 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::EnterHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::ExitHyperCriticalRegion
- CONCRTRM/concurrency::IUMSThreadProxy::IUMSThreadProxy::GetCriticalRegionType
dev_langs: C++
helpviewer_keywords: IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d9d9b200db84ddbf25e514e1432fa0915d5ee383
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="iumsthreadproxy-structure"></a>IUMSThreadProxy 構造体
実行スレッドの抽象化です。 ユーザー モード スケジュール可能 (UMS) スレッドをスケジューラに付与するには、スケジューラ ポリシー要素 `SchedulerKind` の値を `UmsThreadDefault` に設定し、さらに `IUMSScheduler` インターフェイスを実装する必要があります。 UMS スレッドは、Windows 7 以上のバージョンの 64 ビット オペレーティング システムでのみサポートされます。  
  
## <a name="syntax"></a>構文  
  
```
struct IUMSThreadProxy : public IThreadProxy;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Iumsthreadproxy::entercriticalregion](#entercriticalregion)|重要な地域を入力するために呼び出されます。 重要な領域の内部スケジューラでは、領域の中に発生するブロッキング操作を非同期は見られません。 これは、スケジューラがページ フォールトやスレッドの中断、カーネル非同期プロシージャ呼び出し (Apc) など、UMS スレッドでの再入力されませんはことを意味します。|  
|[Iumsthreadproxy::enterhypercriticalregion](#enterhypercriticalregion)|ハイパー クリティカル地域を入力するために呼び出されます。 ハイパー クリティカル領域の場合は、内部スケジューラでは、領域の中に発生するブロッキング操作は見られません。 これは、スケジューラが関数呼び出し、スレッドの中断、カーネル非同期プロシージャ呼び出し (Apc)、およびなど、UMS スレッドがブロックをページ フォールトのロック取得の試行をブロックするため再入力するはないことを意味します。|  
|[Iumsthreadproxy::exitcriticalregion](#exitcriticalregion)|重要な領域を終了するために呼び出されます。|  
|[Iumsthreadproxy::exithypercriticalregion](#exithypercriticalregion)|ハイパー重要な領域を終了するために呼び出されます。|  
|[Iumsthreadproxy::getcriticalregiontype](#getcriticalregiontype)|スレッド プロキシが内で重要な領域の種類を返します。 ハイパー クリティカル領域と重要な領域とし、ハイパー クリティカル領域の場合は、コードを入力した場合は、重要な地域のスーパー セットであるのため`InsideHyperCriticalRegion`が返されます。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [IThreadProxy](ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="entercriticalregion"></a>Iumsthreadproxy::entercriticalregion メソッド  
 重要な地域を入力するために呼び出されます。 重要な領域の内部スケジューラでは、領域の中に発生するブロッキング操作を非同期は見られません。 これは、スケジューラがページ フォールトやスレッドの中断、カーネル非同期プロシージャ呼び出し (Apc) など、UMS スレッドでの再入力されませんはことを意味します。  
  
```
virtual int EnterCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 重要な領域の新しい深度。 重要な領域は再入可能です。  
  
##  <a name="enterhypercriticalregion"></a>Iumsthreadproxy::enterhypercriticalregion メソッド  
 ハイパー クリティカル地域を入力するために呼び出されます。 ハイパー クリティカル領域の場合は、内部スケジューラでは、領域の中に発生するブロッキング操作は見られません。 これは、スケジューラが関数呼び出し、スレッドの中断、カーネル非同期プロシージャ呼び出し (Apc)、およびなど、UMS スレッドがブロックをページ フォールトのロック取得の試行をブロックするため再入力するはないことを意味します。  
  
```
virtual int EnterHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 ハイパー クリティカル領域の新しい深度。 ハイパースレッディング重要な領域は再入可能です。  
  
### <a name="remarks"></a>コメント  
 スケジューラは、このような地域で呼び出すメソッドとロックが取得する新機能について十分に注意する必要があります。 このような領域のコードは、スケジューラはスケジュールによって保持されているロックでブロック、デッドロックが発生したり可能性があります。  
  
##  <a name="exitcriticalregion"></a>Iumsthreadproxy::exitcriticalregion メソッド  
 重要な領域を終了するために呼び出されます。  
  
```
virtual int ExitCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 重要な領域の新しい深度。 重要な領域は再入可能です。  
  
##  <a name="exithypercriticalregion"></a>Iumsthreadproxy::exithypercriticalregion メソッド  
 ハイパー重要な領域を終了するために呼び出されます。  
  
```
virtual int ExitHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 ハイパー クリティカル領域の新しい深度。 ハイパースレッディング重要な領域は再入可能です。  
  
##  <a name="getcriticalregiontype"></a>Iumsthreadproxy::getcriticalregiontype メソッド  
 スレッド プロキシが内で重要な領域の種類を返します。 ハイパー クリティカル領域と重要な領域とし、ハイパー クリティカル領域の場合は、コードを入力した場合は、重要な地域のスーパー セットであるのため`InsideHyperCriticalRegion`が返されます。  
  
```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 内では、重要な領域、スレッド プロキシの種類です。  
  
## <a name="see-also"></a>参照  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IUMSScheduler 構造体](iumsscheduler-structure.md)
