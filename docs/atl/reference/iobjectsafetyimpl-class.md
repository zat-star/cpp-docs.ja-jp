---
title: "IObjectSafetyImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IObjectSafetyImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "コントロール [ATL], 安全な"
  - "IObjectSafety, ATL の実装"
  - "IObjectSafetyImpl クラス"
  - "安全性 (スクリプトと初期化の) (コントロール)"
ms.assetid: 64e32082-d910-4a8a-a5bf-ebed9145359d
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# IObjectSafetyImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`IObjectSafety` インターフェイスの既定の実装を提供して、クライアント側でオブジェクトの安全レベルを取得および設定できるようにします。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]で実行されるアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template <class   
      T  
      , DWORD   
      dwSupportedSafety  
      >  
class IObjectSafetyImpl  
```  
  
#### パラメーター  
 `T`  
 `IObjectSafetyImpl`から派生したクラス。  
  
 *dwSupportedSafety*  
 コントロールでサポートされているセキュリティ オプションを指定します。  次のいずれかの値になります。  
  
-   **INTERFACESAFE\_FOR\_UNTRUSTED\_CALLER** は [SetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::SetInterfaceSafetyOptions.md) のパラメーター `riid` によって識別されるインターフェイス スクリプトに対して安全に行う必要があります。  
  
-   **INTERFACESAFE\_FOR\_UNTRUSTED\_DATA** は `SetInterfaceSafetyOptions` のパラメーター `riid` によって識別されるインターフェイス初期化中に信頼されていないデータに対して安全に行う必要があります。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[IObjectSafetyImpl::GetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::GetInterfaceSafetyOptions.md)|オブジェクトによってサポートされるセキュリティ オプション。または現在のオブジェクトに対して設定されるセキュリティ オプションを取得します。|  
|[IObjectSafetyImpl::SetInterfaceSafetyOptions](../Topic/IObjectSafetyImpl::SetInterfaceSafetyOptions.md)|初期化またはスクリプトにオブジェクトの安全性を作成します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[IObjectSafetyImpl::m\_dwCurrentSafety](../Topic/IObjectSafetyImpl::m_dwCurrentSafety.md)|オブジェクトの現在の安全レベルを格納します。|  
  
## 解説  
 クラス `IObjectSafetyImpl` は `IObjectSafety`の既定の実装を提供します。  `IObjectSafety` のインターフェイスは、クライアントがオブジェクトの安全レベルを取得および設定できるようになります。  たとえば、WebBrowser は、初期化の安全性やスクリプトにセーフにするため **IObjectSafety::SetInterfaceSafetyOptions** を呼び出すことができます。  
  
 **CATID\_SafeForScripting** と **CATID\_SafeForInitializing** のコンポーネント カテゴリの [IMPLEMENTED\_CATEGORY](../Topic/IMPLEMENTED_CATEGORY.md) マクロを使用することでコンポーネントが安全であることを指定する別の方法を用意することに注意してください。  
  
 **関連トピック** [ATL チュートリアル](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md)、[ATL プロジェクトの作成](../../atl/reference/creating-an-atl-project.md)  
  
## 継承階層  
 `IObjectSafety`  
  
 `IObjectSafetyImpl`  
  
## 必要条件  
 **Header:** atlctl.h  
  
## 参照  
 [IObjectSafety Interface](https://msdn.microsoft.com/en-us/library/aa768224.aspx)   
 [クラスの概要](../../atl/atl-class-overview.md)