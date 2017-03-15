---
title: "IUMSThreadProxy 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IUMSThreadProxy
dev_langs:
- C++
helpviewer_keywords:
- IUMSThreadProxy structure
ms.assetid: 61c69b7e-5c37-4048-bcb4-e75c536afd86
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 55ed05f137775e819c81ce231cf8c8ad3a9974f3
ms.lasthandoff: 02/24/2017

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
|[Iumsthreadproxy::entercriticalregion メソッド](#entercriticalregion)|重要な領域を入力するために呼び出されます。 クリティカル領域内、スケジューラは、領域の中に発生する非同期のブロック操作を確認しません。 これは、スケジューラがページ フォールトやスレッドの中断、カーネル非同期プロシージャ コール (Apc) など、UMS スレッドでの再入力しないはことを意味します。|  
|[Iumsthreadproxy::enterhypercriticalregion メソッド](#enterhypercriticalregion)|ハイパー クリティカル領域を入力するために呼び出されます。 ハイパー クリティカル領域内、スケジューラでは、領域の中に発生するすべてのブロック操作は見られません。 これは、スケジューラが関数の呼び出し、スレッドの中断、カーネル非同期プロシージャ コール (Apc)、およびなど、UMS スレッドがブロック、ページ フォールトのロックの取得の試行をブロックするため再入力するはないことを意味します。|  
|[Iumsthreadproxy::exitcriticalregion メソッド](#exitcriticalregion)|重要な領域を終了するために呼び出されます。|  
|[Iumsthreadproxy::exithypercriticalregion メソッド](#exithypercriticalregion)|ハイパー クリティカル領域を終了するために呼び出されます。|  
|[Iumsthreadproxy::getcriticalregiontype メソッド](#getcriticalregiontype)|内で、スレッド プロキシは、クリティカル領域の種類を返します。 クリティカル領域とし、ハイパー クリティカル領域では、コードを入力した場合、ハイパー クリティカル領域はクリティカル領域のスーパー セットであるのため`InsideHyperCriticalRegion`が返されます。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [IThreadProxy](ithreadproxy-structure.md)  
  
 `IUMSThreadProxy`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-nameentercriticalregiona--iumsthreadproxyentercriticalregion-method"></a><a name="entercriticalregion"></a>Iumsthreadproxy::entercriticalregion メソッド  
 重要な領域を入力するために呼び出されます。 クリティカル領域内、スケジューラは、領域の中に発生する非同期のブロック操作を確認しません。 これは、スケジューラがページ フォールトやスレッドの中断、カーネル非同期プロシージャ コール (Apc) など、UMS スレッドでの再入力しないはことを意味します。  
  
```
virtual int EnterCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 クリティカル領域の新しい深度。 クリティカル領域は再入可能です。  
  
##  <a name="a-nameenterhypercriticalregiona--iumsthreadproxyenterhypercriticalregion-method"></a><a name="enterhypercriticalregion"></a>Iumsthreadproxy::enterhypercriticalregion メソッド  
 ハイパー クリティカル領域を入力するために呼び出されます。 ハイパー クリティカル領域内、スケジューラでは、領域の中に発生するすべてのブロック操作は見られません。 これは、スケジューラが関数の呼び出し、スレッドの中断、カーネル非同期プロシージャ コール (Apc)、およびなど、UMS スレッドがブロック、ページ フォールトのロックの取得の試行をブロックするため再入力するはないことを意味します。  
  
```
virtual int EnterHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 ハイパー クリティカル領域の新しい深度。 ハイパースレッディング クリティカル領域は再入可能です。  
  
### <a name="remarks"></a>コメント  
 スケジューラは、どのようなメソッドを呼び出すし、ロックでは、このような領域が取得するか十分に注意する必要があります。 このような領域のコードは、ロックが保持しているもの、スケジューラはスケジュールでブロックする場合は、デッドロックが発生したり可能性があります。  
  
##  <a name="a-nameexitcriticalregiona--iumsthreadproxyexitcriticalregion-method"></a><a name="exitcriticalregion"></a>Iumsthreadproxy::exitcriticalregion メソッド  
 重要な領域を終了するために呼び出されます。  
  
```
virtual int ExitCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 クリティカル領域の新しい深度。 クリティカル領域は再入可能です。  
  
##  <a name="a-nameexithypercriticalregiona--iumsthreadproxyexithypercriticalregion-method"></a><a name="exithypercriticalregion"></a>Iumsthreadproxy::exithypercriticalregion メソッド  
 ハイパー クリティカル領域を終了するために呼び出されます。  
  
```
virtual int ExitHyperCriticalRegion() = 0;
```  
  
### <a name="return-value"></a>戻り値  
 ハイパー クリティカル領域の新しい深度。 ハイパースレッディング クリティカル領域は再入可能です。  
  
##  <a name="a-namegetcriticalregiontypea--iumsthreadproxygetcriticalregiontype-method"></a><a name="getcriticalregiontype"></a>Iumsthreadproxy::getcriticalregiontype メソッド  
 内で、スレッド プロキシは、クリティカル領域の種類を返します。 クリティカル領域とし、ハイパー クリティカル領域では、コードを入力した場合、ハイパー クリティカル領域はクリティカル領域のスーパー セットであるのため`InsideHyperCriticalRegion`が返されます。  
  
```
virtual CriticalRegionType GetCriticalRegionType() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 クリティカル領域、スレッド プロキシの種類では、内です。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [IUMSScheduler 構造体](iumsscheduler-structure.md)

