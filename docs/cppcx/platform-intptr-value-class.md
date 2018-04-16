---
title: "Platform::intptr 値クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformIntPtr::IntPtr
- VCCORLIB/PlatformIntPtr::op_explicit Operator
- VCCORLIB/PlatformIntPtr::ToInt32
dev_langs:
- C++
helpviewer_keywords:
- Platform::IntPtr Struct
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 93263e1347857b9c78a62852bea96e10c8d68fac
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="platformintptr-value-class"></a>Platform::IntPtr 値クラス
サイズがプラットフォームに特有の (32 ビットまたは 64 ビット)、符号付きポインターまたはハンドルを表します。  
  
## <a name="syntax"></a>構文  
  
```cpp  
public value struct IntPtr  
```  
  
### <a name="members"></a>メンバー  
 IntPtr には、次のメンバーがあります。  
  
|メンバー|説明|  
|------------|-----------------|  
|[IntPtr::IntPtr](#ctor)|IntPtr の新しいインスタンスを初期化します。|  
|[IntPtr::op_explicit 演算子](#op-explicit)|指定されたパラメーターを IntPtr、または IntPtr 値へのポインターに変換します。|  
|[IntPtr::ToInt32](#toint32)|現在の IntPtr を 32 ビット整数に変換します。|  
  
### <a name="requirements"></a>必要条件  
 **クライアントがサポートされる最小:** Windows 8  
  
 **サポートされているサーバーの最小値:** Windows Server 2012  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  

## <a name="ctor"> </a> IntPtr::IntPtr コンストラクター
指定された値を持つ IntPtr の新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
IntPtr( __int64 handle-or-pointer );   IntPtr( void* value );   IntPtr( int 32-bit_value );  
```  
  
### <a name="parameters"></a>パラメーター  
 value  
 64 ビットのハンドルまたはポインター、または 64 ビット値へのポインター、または 64 ビット値に変換できる 32 ビット値。  
  


## <a name="op-explicit"> </a> IntPtr::op_explicit 演算子
指定されたパラメーターを IntPtr、または IntPtr 値へのポインターに変換します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );  
```  
  
### <a name="parameters"></a>パラメーター  
 value1  
 ハンドルまたは IntPtr へのポインター。  
  
 value2  
 IntPtr に変換できる 32 ビット整数。  
  
 value3  
 IntPtr。  
  
### <a name="return-value"></a>戻り値  
 1 番目と 2 番目の演算子は IntPtr を返します。 3 番目の演算子は、現在の IntPtr によって表される値へのポインターを返します。  
  


## <a name="toint32"> </a> Intptr::toint32 メソッド
現在の IntPtr 値を 32 ビット整数に変換します。  
  
### <a name="syntax"></a>構文  
  
```cpp  
int32 IntPtr::ToInt32();  
```  
  
### <a name="return-value"></a>戻り値  
 32 ビット整数。  
  
  
## <a name="see-also"></a>参照  
 [Platform 名前空間](../cppcx/platform-namespace-c-cx.md)