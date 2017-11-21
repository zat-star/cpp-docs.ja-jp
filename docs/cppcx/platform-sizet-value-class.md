---
title: "Platform::sizet 値クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/PlatformSizeT::SizeT constructor
dev_langs: C++
helpviewer_keywords: Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 18001661b0862f19e3c002f4c4e60efdf68c9e30
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="platformsizet-value-class"></a>Platform::SizeT 値クラス
オブジェクトのサイズを表します。 SizeT は符号なしのデータ型です。  
  
## <a name="syntax"></a>構文  
  
```cpp  
public ref class SizeT sealed : ValueType  
```  
  
### <a name="members"></a>メンバー  
  
|メンバー|説明|  
|------------|-----------------|  
|[SizeT::SizeT コンストラクター](#ctor)|指定された値で、クラスの新しいインスタンスを初期化します。|  
  
### <a name="requirements"></a>要件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  

 ## <a name="ctor"></a>Sizet::sizet コンス トラクター
指定された値を持つ SizeT の新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
SizeT( uint32 value1 );   SizeT( void* value2 );  
```  
  
### <a name="parameters"></a>パラメーター  
 value1  
 符号なし 32 ビット値。  
  
 value2  
 符号なし 32 ビット値へのポインター。  
  
  
## <a name="see-also"></a>関連項目  
 [Platform 名前空間](../cppcx/platform-namespace-c-cx.md)