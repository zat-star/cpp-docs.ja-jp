---
title: "progress_reporter クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
dev_langs: C++
helpviewer_keywords: progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1dcdba2e5242dcd750eea42b61575ebea921d7b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="progressreporter-class"></a>progress_reporter クラス
progress reporter クラスは、特定の型の進行状況の通知をレポートできます。 各 progress_reporter オブジェクトが、特定の非同期アクションまたは操作にバインドされます。  
  
## <a name="syntax"></a>構文  
  
```
template<typename _ProgressType>
class progress_reporter;
```  
  
#### <a name="parameters"></a>パラメーター  
 `_ProgressType`  
 progress_reporter クラスによって報告される進行状況の各通知のペイロードの種類。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[progress_reporter](#ctor)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[レポート](#report)|progress reporter クラスのバインド先となる非同期アクションまたは非同期操作に、進行状況レポートを送信します。|  
  
## <a name="remarks"></a>コメント  
 このクラスは、Windows ストア アプリでのみ使用できます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `progress_reporter`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** ppltasks.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>progress_reporter 

```
progress_reporter();
```  
  
##  <a name="report"></a>レポート 

 progress reporter クラスのバインド先となる非同期アクションまたは非同期操作に、進行状況レポートを送信します。  
  
```
void report(const _ProgressType& val) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `val`  
 進行状況を示す通知によって報告されるペイロード。  
  
## <a name="see-also"></a>参照  
 [concurrency 名前空間](concurrency-namespace.md)
