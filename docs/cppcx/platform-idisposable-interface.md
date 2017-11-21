---
title: "Platform::idisposable インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::IDisposable
dev_langs: C++
helpviewer_keywords: Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 0bc36087532bbac86b5891408fc3e4bea30c0256
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="platformidisposable-interface"></a>Platform::IDisposable インターフェイス
アンマネージ リソースを解放するために使用されます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
public interface class IDisposable  
```  
  
## <a name="attributes"></a>属性  
 **GuidAttribute**("de0cbaea-8065-4a45-b196-c9d443f9bab3")  
  
 **VersionAttribute**(NTDDI_WIN8)  
  
### <a name="members"></a>メンバー  
 IDisposable インターフェイスは IUnknown インターフェイスから継承します。 また IDisposable には次の種類のメンバーもあります。  
  
 **メソッド**  
  
 IDisposable インターフェイスには、次のメソッドがあります。  
  
|メソッド|説明|  
|------------|-----------------|  
|Dispose|アンマネージ リソースを解放するために使用されます。|  
  
### <a name="requirements"></a>要件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform