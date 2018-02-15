---
title: "Platform::callbackcontext 列挙 |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
dev_langs:
- C++
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f9d34f7ef8a953ce60972c27b34e257ea66d62d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext 列挙型
コールバック関数 (イベント ハンドラー) が実行するスレッド コンテキストを指定します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
enum class CallbackContext {};  
```  
  
### <a name="members"></a>メンバー  
  
|型コード|説明|  
|---------------|-----------------|  
|どれでも可|コールバック関数は、任意のスレッド コンテキストで実行できます。|  
|同|コールバック関数は、非同期操作を開始したスレッド コンテキストでのみ実行できます。|  
  
### <a name="requirements"></a>必要条件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd