---
title: "IDispatchImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDispatchImpl"
  - "ATL.IDispatchImpl"
  - "ATL::IDispatchImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "デュアル インターフェイス, クラス"
  - "IDispatch クラス サポート ATL"
  - "IDispatchImpl クラス"
ms.assetid: 8108eb36-1228-4127-a203-3ab5ba488892
caps.latest.revision: 27
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# IDispatchImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

デュアル インターフェイスの `IDispatch` 部分の既定の実装を提供します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
template<  
   class T,  
   const IID* piid= &__uuidof(T),  
   const GUID* plibid = &CAtlModule::m_libid,  
   WORD wMajor = 1,  
   WORD wMinor = 0,  
   class tihclass = CComTypeInfoHolder   
>   
class ATL_NO_VTABLE IDispatchImpl :  
   public T  
```  
  
#### パラメーター  
 \[入力\] `T`  
 デュアル インターフェイス。  
  
 \[入力\] `piid`  
 `T` の IID へのポインター。  
  
 \[入力\] `plibid`  
 インターフェイスに関する情報を保持するタイプ ライブラリの LIBID へのポインター。  既定では、サーバーレベルのタイプ ライブラリが渡されます。  
  
 \[入力\] `wMajor`  
 タイプ ライブラリのメジャー バージョン。  既定値は 1 です。  
  
 \[入力\] `wMinor`  
 タイプ ライブラリのマイナー バージョン。  既定値は 0 です。  
  
 \[入力\] `tihclass`  
 `T` の型情報の管理に使用されるクラス。  既定値は `CComTypeInfoHolder` です。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[IDispatchImpl::IDispatchImpl](../Topic/IDispatchImpl::IDispatchImpl.md)|コンストラクターです。  デュアル インターフェイスの型情報を管理するプロテクト メンバー変数の `AddRef` を呼び出します。  デストラクターは `Release`を呼び出します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IDispatchImpl::GetIDsOfNames](../Topic/IDispatchImpl::GetIDsOfNames.md)|一連の名前を対応する一連のディスパッチ識別子に割り当てます。|  
|[IDispatchImpl::GetTypeInfo](../Topic/IDispatchImpl::GetTypeInfo.md)|デュアル インターフェイスの型情報を取得します。|  
|[IDispatchImpl::GetTypeInfoCount](../Topic/IDispatchImpl::GetTypeInfoCount.md)|デュアル インターフェイスで使用できるタイプ情報があるかどうかを判断します。|  
|[IDispatchImpl::Invoke](../Topic/IDispatchImpl::Invoke.md)|デュアル インターフェイスによって公開されるメソッドやプロパティへのアクセスを提供します。|  
  
## 解説  
 `IDispatchImpl` は、オブジェクトのデュアル インターフェイスの `IDispatch` 部分に対する既定の実装を提供します。  デュアル インターフェイスは、`IDispatch` から派生され、オートメーション互換型だけを使います。  ディスパッチ インターフェイスと同様に、デュアル インターフェイスでも事前バインディングと遅延バインディングがサポートされますが、デュアル インターフェイスでは vtable バインディングもサポートされます。  
  
 `IDispatchImpl` の一般的な実装例を次に示します。  
  
 [!code-cpp[NVC_ATL_COM#47](../../atl/codesnippet/CPP/idispatchimpl-class_1.h)]  
  
 既定では、`IDispatchImpl` クラスはレジストリから `T` の型情報を検索します。  登録されていないインターフェイスを実装する場合は、定義済みのバージョン番号を使用することで、レジストリにアクセスせずに `IDispatchImpl` クラスを使用できます。  `wMajor` の値が 0xFFFF で `wMinor` の値が 0xFFFF の `IDispatchImpl` オブジェクトを作成すると、`IDispatchImpl` クラスはレジストリではなく .dll ファイルからタイプ ライブラリを取得します。  
  
 `IDispatchImpl` は、デュアル インターフェイスのタイプ情報を管理する `CComTypeInfoHolder` 型の静的メンバーを保持します。  同一のデュアル インターフェイスを実装する複数のオブジェクトがある場合は、`CComTypeInfoHolder` の 1 つのインスタンスだけが使われます。  
  
## 継承階層  
 `T`  
  
 `IDispatchImpl`  
  
## 必要条件  
 **ヘッダー:** atlcom.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)