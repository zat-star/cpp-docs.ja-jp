---
title: "&lt;future&gt; 列挙型 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: 835abafde46858bd108dfa648a246345bd254eaf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ltfuturegt-enums"></a>&lt;future&gt; 列挙型
||||  
|-|-|-|  
|[future_errc](#future_errc)|[future_status](#future_status)|[起動します。](#launch)|  
  
##  <a name="future_errc"></a>  future_errc 列挙型  
 [future_error](../standard-library/future-error-class.md) クラスによって報告されるすべてのエラーのシンボル名を提供します。  
  
class future_errc { broken_promise, future_already_retrieved, promise_already_satisfied, no_state };  
  
##  <a name="future_status"></a>  future_status 列挙型  
 期限が設定された wait 関数から返される理由のシンボル名を提供します。  
  
```
enum future_status{    ready,
    timeout,
 deferred};
```  
  
##  <a name="launch"></a>  launch 列挙型  
 テンプレート関数 [async](../standard-library/future-functions.md#async) で使用できるモードを示すビットマスク型を表します。  
  
class launch{ async, deferred };  
  
## <a name="see-also"></a>参照  
 [\<future>](../standard-library/future.md)



