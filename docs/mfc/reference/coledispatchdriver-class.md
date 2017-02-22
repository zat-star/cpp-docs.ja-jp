---
title: "COleDispatchDriver クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDispatchDriver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "オートメーション クライアント, 実装 (オートメーションを)"
  - "COleDispatchDriver クラス"
  - "OLE ディスパッチ インターフェイス"
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# COleDispatchDriver クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE オートメーションのクライアント側を実装します。  
  
## 構文  
  
```  
class COleDispatchDriver  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleDispatchDriver::COleDispatchDriver](../Topic/COleDispatchDriver::COleDispatchDriver.md)|`COleDispatchDriver` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleDispatchDriver::AttachDispatch](../Topic/COleDispatchDriver::AttachDispatch.md)|`COleDispatchDriver` のオブジェクトへの `IDispatch` の接続をアタッチします。|  
|[COleDispatchDriver::CreateDispatch](../Topic/COleDispatchDriver::CreateDispatch.md)|`IDispatch` の接続を作成し、`COleDispatchDriver` のオブジェクトにアタッチします。|  
|[COleDispatchDriver::DetachDispatch](../Topic/COleDispatchDriver::DetachDispatch.md)|これを解放せずに `IDispatch` の接続を、デタッチします。|  
|[COleDispatchDriver::GetProperty](../Topic/COleDispatchDriver::GetProperty.md)|オートメーション プロパティを取得します。|  
|[COleDispatchDriver::InvokeHelper](../Topic/COleDispatchDriver::InvokeHelper.md)|オートメーション メソッドを呼び出すためのヘルパー。|  
|[COleDispatchDriver::ReleaseDispatch](../Topic/COleDispatchDriver::ReleaseDispatch.md)|`IDispatch` の接続を解放します。|  
|[COleDispatchDriver::SetProperty](../Topic/COleDispatchDriver::SetProperty.md)|オートメーション プロパティを設定します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[COleDispatchDriver::operator \=](../Topic/COleDispatchDriver::operator%20=.md)|`COleDispatchDriver` のオブジェクトにソースの値をコピーします。|  
|[COleDispatchDriver::operator LPDISPATCH](../Topic/COleDispatchDriver::operator%20LPDISPATCH.md)|基になる `IDispatch` のポインターにアクセスします。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[COleDispatchDriver::m\_bAutoRelease](../Topic/COleDispatchDriver::m_bAutoRelease.md)|`IDispatch` を `ReleaseDispatch` 中に解放するか、またはオブジェクトに破棄するかどうかを指定します。|  
|[COleDispatchDriver::m\_lpDispatch](../Topic/COleDispatchDriver::m_lpDispatch.md)|この `COleDispatchDriver`にアタッチされている `IDispatch` のインターフェイスへのポインターを示します。|  
  
## 解説  
 `COleDispatchDriver` には、基本クラスはありません。  
  
 OLE ディスパッチ インターフェイスは、オブジェクトのメソッドとプロパティにアクセスできます。  `COleDispatchDriver` の追加、デタッチのメンバー関数は、を作成して、型 `IDispatch`のディスパッチ接続を解放します。  他のメンバー関数は **IDispatch::Invoke**を呼び出すことが簡単にするには、可変個引数リストを使用します。  
  
 このクラスを直接使用できますが、クラス追加ウィザードが作成するクラスによってのみ一般的に使用されます。  作成すると、新しい C\+\+ は、新しいクラス派生クラスをタイプ ライブラリをインポートしてから `COleDispatchDriver`。  
  
 `COleDispatchDriver`の使用の詳細については、次のトピックを参照:  
  
-   [オートメーション クライアント](../../mfc/automation-clients.md)  
  
-   [オートメーション サーバー](../../mfc/automation-servers.md)  
  
## 継承階層  
 `COleDispatchDriver`  
  
## 必要条件  
 **ヘッダー :** afxdisp.h  
  
## 参照  
 [MFC CALCDRIV サンプル](../../top/visual-cpp-samples.md)   
 [MFC の ACDUAL サンプル](../../top/visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)