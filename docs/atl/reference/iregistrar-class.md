---
title: "IRegistrar インターフェイス |Microsoft ドキュメント"
ms.custom: 
ms.date: 2/1/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRegistrar
- ATLIFASE/ATL::IRegistrar
- ATLIFASE/ATL::IRegistrar::ResourceRegisterSz
- ATLIFASE/ATL::IRegistrar::ResourceUnregisterSz
- ATLIFASE/ATL::IRegistrar::FileRegister
- ATLIFASE/ATL::IRegistrar::FileUnregister
- ATLIFASE/ATL::IRegistrar::StringRegister
- ATLIFASE/ATL::IRegistrar::StringUnregister
- ATLIFASE/ATL::IRegistrar::ResourceRegister
- ATLIFASE/ATL::IRegistrar::ResourceUnregister
dev_langs:
- C++
helpviewer_keywords:
- Iregistrar Interface
ms.assetid: e88c04b7-0c93-4ae8-aeb9-ecd78f87421e
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 199cdfd91a7d1b9882b57118c852352f6fdda43e
ms.openlocfilehash: e73e095d253d5ec5ca53e4e446019b2da79e5d39
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="iregistrar-interface"></a>IRegistrar インターフェイス
このインターフェイスは atliface.h で定義され、内部関数によって使用される不要メンバーなど[ため](catlmodule-class.md#updateregistryfromresourced)です。   
  
## <a name="syntax"></a>構文  
  
```
typedef interface IRegistrar IRegistrar;
```  
## <a name="remarks"></a>コメント
トピックを参照して[置き換え可能パラメーターを使用して (レジストラーのプリプロセッサ)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)詳細です。  

## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[IRegistrar::ResourceRegisterSz](#resourceregistersz)|リソースを登録します。 |  
|[IRegistrar::ResourceUnregisterSz](#resourceunregistersz)| リソースの登録を解除します。|  
|[IRegistrar::FileRegister](#fileregister)|ファイルを登録します。|  
|[IRegistrar::FileUnregister](#fileunregister)|ファイルを登録解除します。|  
|[IRegistrar::StringRegister](#stringregister)|文字列を登録します。|  
|[IRegistrar::StringUnregister](#stringunregister)|文字列の登録を解除します。|  
|[IRegistrar::ResourceRegister](#resourceregister)|リソースを登録します。|  
|[IRegistrar::ResourceUnregister](#resourceunregister)|リソースの登録を解除します。| 
  

 
## <a name="requirements"></a>要件  
 **ヘッダー:** atlifase.h  
  
##  <a name="resourceregistersz"></a>IRegistrar::ResourceRegisterSz 
 リソースを登録します。  
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
  
 
  
##  <a name="resourceunregistersz"></a>IRegistrar::ResourceUnregisterSz  
 リソースの登録を解除します。
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
  
  
##  <a name="fileregister"></a>IRegistrar::FileRegister  
ファイルを登録します。
  
```
virtual HRESULT STDMETHODCALLTYPE FileRegister( 
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```  
  
  
##  <a name="fileunregister"></a>IRegistrar::FileUnregister  
ファイルを登録解除します。

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister( 
    */ _In_z_ LPCOLESTR fileName) = 0;
```  
  
 
##  <a name="stringregister"></a>IRegistrar::StringRegister  
  指定された文字列データを登録します。
```
virtual HRESULT STDMETHODCALLTYPE StringRegister( 
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```  
  
##  <a name="stringunregister"></a>IRegistrar::StringUnregister
 指定された文字列データの登録を解除します。  
  
```
virtualHRESULT STDMETHODCALLTYPE StringUnregister( 
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```  

  
##  <a name="resourceregister"></a>IRegistrar::ResourceRegister  
 リソースを登録します。  
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
   
  
##  <a name="resourceunregister"></a>IRegistrar::ResourceUnregister  
 リソースの登録を解除します。  
  
```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0; 
```  
 
## <a name="see-also"></a>関連項目  
 [置き換え可能パラメーター (レジストラーのプリプロセッサ) を使用します。](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [モジュール クラス](../../atl/atl-module-classes.md)   
 [レジストリ コンポーネント (レジストラー)](../../atl/atl-registry-component-registrar.md)  

