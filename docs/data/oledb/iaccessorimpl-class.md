---
title: "IAccessorImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IAccessorImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAccessorImpl クラス"
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAccessorImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) インターフェイスの実装を提供します。  
  
## 構文  
  
```  
template <  
   class T,   
   class BindType = ATLBINDINGS,   
   class BindingVector = CAtlMap <   
      HACCESSOR hAccessor,   
      BindType* pBindingsStructure   
   >   
>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
#### パラメーター  
 `T`  
 行セットまたはコマンド オブジェクト クラス。  
  
 `BindType`  
 バインディング情報のストレージ ユニット。  既定では **ATLBINDINGS** 構造です \(atldb.h を参照してください。  
  
 `BindingVector`  
 列情報のストレージ ユニット。  既定では、キー要素が **HACCESSOR** 値要素が `BindType` 構造体へのポインターである [CAtlMap](../../atl/reference/catlmap-class.md) です。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)|コンストラクターです。|  
  
### インターフェイス メソッド  
  
|||  
|-|-|  
|[AddRefAccessor](../../data/oledb/iaccessorimpl-addrefaccessor.md)|既存のアクセサーの参照カウントをインクリメントします。|  
|[CreateAccessor](../../data/oledb/iaccessorimpl-createaccessor.md)|バインディングのセットからアクセサーを作成します。|  
|[GetBindings](../Topic/IAccessorImpl::GetBindings.md)|アクセサーのバインディングを返します。|  
|[ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)|アクセサーを解放します。|  
  
## 解説  
 これは、行セット オブジェクトとコマンドで必須です。  OLE DB は、プロバイダーが **HACCESSOR**を実装するように必要があります。[DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) 構造体の配列にタグです。  `IAccessorImpl` に用意されている**HACCESSOR**s は `BindType` 構造体のアドレスです。  既定で、`BindType` は `IAccessorImpl` のテンプレート定義の **ATLBINDINGS** として定義されます。  `BindType` は **DBBINDING** の配列の要素数を追跡するために `IAccessorImpl` で使用される機能を提供しますが、参照カウントとアクセサーのフラグ。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)