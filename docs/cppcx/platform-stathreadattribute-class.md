---
title: "Platform::stathreadattribute クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Platform
- COLLECTION/Platform::Platform::STAThreadAttribute constructor 1
- COLLECTION/Platform::Platform::STAThreadAttribute::Equals
- COLLECTION/Platform::Platform::STAThreadAttribute::GetHashCode
- COLLECTION/Platform::Platform::STAThreadAttribute::ToString
dev_langs: C++
helpviewer_keywords: Platform::STAThreadAttribute Class
ms.assetid: f97960fc-e673-4d9e-910a-54c8415411c4
caps.latest.revision: "3"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b1c2b8c38d672b6bd3ecd0fcafb54a9b6e723202
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="platformstathreadattribute-class"></a>Platform::STAThreadAttribute クラス
アプリケーションのスレッド モデルがシングル スレッド アパートメント (STA) であることを示します。  
  
## <a name="syntax"></a>構文  
  
```  
public ref class STAThreadAttribute sealed : Attribute  
```  
  
### <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[STAThreadAttribute コンストラクター 1](#ctor)|クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
 STAThreadAttribute 属性が継承[platform::object クラス](../cppcx/platform-object-class.md)です。 また STAThreadAttribute は次のメンバーもオーバーロードしたり、含んだりします。  
  
|name|説明|  
|----------|-----------------|  
|[STAThreadAttribute::Equals](#equals)|指定したオブジェクトが、現在のオブジェクトと等しいかどうかを判断します。|  
|[STAThreadAttribute::GetHashCode](#gethashcode)|このインスタンスのハッシュ コードを返します。|  
|[STAThreadAttribute::ToString](#tostring)|現在のオブジェクトを表す文字列を返します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `Platform`  
  
### <a name="requirements"></a>必要条件  
 **ヘッダー:** collection.h  
  
 **名前空間:** Platform  



## <a name="ctor"></a> STAThreadAttribute constructor
STAThreadAttribute クラスの新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
public:STAThreadAttribute()  
```  
  


## <a name="equals"></a>STAThreadAttribute::Equals
指定したオブジェクトが、現在のオブジェクトと等しいかどうかを判断します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
public:virtual override bool Equals(  Object^ obj)  
```  
  
### <a name="parameters"></a>パラメーター  
 obj  
 比較対象のオブジェクト。  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが等しい場合は `true`。それ以外の場合は `false`。  
  


## <a name="gethashcode"></a>STAThreadAttribute::GetHashCode
このインスタンスのハッシュ コードを返します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
public:int GetHashCode()  
```  
  
### <a name="return-value"></a>戻り値  
 対象のインスタンスのハッシュ コード。  
  


## <a name="tostring"></a>STAThreadAttribute::ToString
現在のオブジェクトを表す文字列を返します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
public:String^ ToString()  
```  
  
### <a name="return-value"></a>戻り値  
 現在のオブジェクトを表す文字列。  
  

  
## <a name="see-also"></a>参照  
 [プラットフォーム Namespace](platform-namespace-c-cx.md)