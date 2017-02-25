---
title: "IRunnableObjectImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IRunnableObjectImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コンテナー, 実行 (コントロールを)"
  - "コントロール [ATL], 実行"
  - "コントロール [C++], コンテナー (ATL で実行中の)"
  - "IRunnableObject, ATL の実装"
  - "IRunnableObjectImpl クラス"
ms.assetid: 305c7c3b-889e-49dd-aca1-34379c1b9931
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IRunnableObjectImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、**IUnknown** を実装し、[IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) インターフェイスの既定の実装を提供します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template< class   
      T  
      >  
class IRunnableObjectImpl  
```  
  
#### パラメーター  
 `T`  
 `IRunnableObjectImpl`から派生したクラス。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IRunnableObjectImpl::GetRunningClass](../Topic/IRunnableObjectImpl::GetRunningClass.md)|実行中のコントロールの CLSID を返します。  ATL 実装は、`GUID_NULL` に CLSID を設定し、**E\_UNEXPECTED**を返します。|  
|[IRunnableObjectImpl::IsRunning](../Topic/IRunnableObjectImpl::IsRunning.md)|コントロールが実行されているかどうかを判定します。  ATL 実装は、**TRUE**を返します。|  
|[IRunnableObjectImpl::LockRunning](../Topic/IRunnableObjectImpl::LockRunning.md)|実行状態にコントロールをロックします。  ATL 実装は、`S_OK`を返します。|  
|[IRunnableObjectImpl::Run](../Topic/IRunnableObjectImpl::Run.md)|コントロールを実行するように強制します。  ATL 実装は、`S_OK`を返します。|  
|[IRunnableObjectImpl::SetContainedObject](../Topic/IRunnableObjectImpl::SetContainedObject.md)|コントロールが埋め込まれていることを示します。  ATL 実装は、`S_OK`を返します。|  
  
## 解説  
 [IRunnableObject](http://msdn.microsoft.com/library/windows/desktop/ms692783) のインターフェイスは、実行するようにコントロールが実行されているかどうかを判断します。コンテナーは、強制するか、または実行状態にロックするできます。  クラス `IRunnableObjectImpl` は、このインターフェイスの既定の実装を提供し、デバッグ ビルドでダンプ デバイスに情報を送信して **IUnknown** を実装します。  
  
 **関連トピック** [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)、[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## 継承階層  
 `IRunnableObject`  
  
 `IRunnableObjectImpl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [CComControl クラス](../../atl/reference/ccomcontrol-class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)