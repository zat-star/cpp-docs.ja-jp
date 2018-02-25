---
title: "runtime_exception クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
dev_langs:
- C++
helpviewer_keywords:
- runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 678f0a93577a6e30afbc5e0c6d83aca6b6a7bedc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="runtimeexception-class"></a>runtime_exception クラス
C++ Accelerated Massive Parallelism (AMP) ライブラリ内の例外の基本型。  
  
### <a name="syntax"></a>構文  
  
```  
class runtime_exception : public std::exception;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[runtime_exception コンス トラクター](#ctor)|`runtime_exception` クラスの新しいインスタンスを初期化します。|  
|[~ runtime_exception デストラクター](#dtor)|`runtime_exception` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[get_error_code](#runtime_exception__get_error_code)|例外の原因となったエラー コードを返します。|  

  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator=](#operator_eq)|指定された `runtime_exception` オブジェクトの内容をこのオブジェクトにコピーします。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `runtime_exception`  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  

## <a name="runtime_exception__ctor">runtime_exception コンス トラクター</a>  
クラスの新しいインスタンスを初期化します。  
  
### <a name="syntax"></a>構文  
  
```  
runtime_exception(  
    const char * _Message,  
    HRESULT _Hresult ) throw();  
  
explicit runtime_exception(  
    HRESULT _Hresult ) throw();  
  
runtime_exception(  
    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 この例外の原因になったエラーの説明。  
  
 `_Hresult`  
 この例外の原因になったエラーの HRESULT。  
  
 `_Other`  
 コピーする `runtime_exception` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 `runtime_exception` オブジェクト。  

## <a name="dtor">~ runtime_exception デストラクター</a>  
オブジェクトを破棄します。  
  
### <a name="syntax"></a>構文  
  
```  
virtual ~runtime_exception() throw();  
```  
  
## <a name="runtime_exception__get_error_code"></a>  get_error_code   
例外の原因となったエラー コードを返します。  
  
### <a name="syntax"></a>構文  
  
```  
HRESULT get_error_code() const throw();  
```  
  
### <a name="return-value"></a>戻り値  
 この例外の原因になったエラーの HRESULT。  
  
## <a name="runtime_exception__operator_eq"></a>  operator=   
  指定された `runtime_exception` オブジェクトの内容をこのオブジェクトにコピーします。  
  
### <a name="syntax"></a>構文  
  
```  
runtime_exception & operator= (    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 コピーする `runtime_exception` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
 この `runtime_exception` オブジェクトへの参照。  
  

  
## <a name="see-also"></a>参照  
 [Concurrency 名前空間 (C++ AMP)](concurrency-namespace-cpp-amp.md)
