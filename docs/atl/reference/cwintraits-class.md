---
title: "CWinTraits クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CWinTraits"
  - "CMDIChildWinTraits"
  - "ATL.CWinTraits"
  - "CFrameWinTraits"
  - "ATL::CWinTraits"
  - "CControlWinTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CControlWinTraits クラス"
  - "CFrameWinTraits クラス"
  - "CMDIChildWinTraits クラス"
  - "CWinTraits クラス"
  - "ウィンドウ スタイル, 既定値 (ATL の)"
ms.assetid: f78f486e-6d9c-42c6-8e86-371e05aa7e59
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinTraits クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、ウィンドウ オブジェクトの作成に使用する、スタイルを標準化するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template <  
DWORD t_dwStyle= 0,  
DWORD t_dwExStyle= 0  
>  
class CWinTraits  
```  
  
#### パラメーター  
 `t_dwStyle`  
 標準のウィンドウ スタイルは簡素化されます。  
  
 `t_dwExStyle`  
 拡張ウィンドウ スタイルは簡素化されます。  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CWinTraits::GetWndExStyle](../Topic/CWinTraits::GetWndExStyle.md)|\(静的関数\) `CWinTraits` のオブジェクトの拡張スタイルを取得します。|  
|[CWinTraits::GetWndStyle](../Topic/CWinTraits::GetWndStyle.md)|\(静的関数\) `CWinTraits` のオブジェクトの標準スタイルを取得します。|  
  
## 解説  
 [ウィンドウの特性](../../atl/understanding-window-traits.md) のこのクラスは、ATL ウィンドウ オブジェクトの作成に使用するスタイルを標準化するための簡単な方法を提供します。  標準既定値となるウィンドウ クラスのインスタンスに使用する拡張スタイルを指定するために [CWindowImpl](../Topic/CWindowImpl%20Class.md) にテンプレート パラメーターまたは ATL ウィンドウ クラスの一つとしてこのクラスの特殊化を使用します。  
  
 他のスタイルが [CWindowImpl::Create](../Topic/CWindowImpl::Create.md)への呼び出しで指定されていない場合にのみ使用される既定のウィンドウ スタイルを指定する場合は、このテンプレートを使用します。  
  
 ATL はウィンドウ スタイルの一般的な組み合わせに、このテンプレートの 3 種類の定義済み特殊な形式を指定します:  
  
 `CControlWinTraits`  
 標準のコントロール ウィンドウを目的に設計されています。  次の標準スタイルが使用されます: **WS\_CHILD**、**WS\_VISIBLE**、**WS\_CLIPCHILDREN**と **WS\_CLIPSIBLINGS**。  拡張スタイルはありません。  
  
 `CFrameWinTraits`  
 標準的なフレーム ウィンドウを目的に設計されています。  使用される標準のスタイルは次のとおりです。: **WS\_OVERLAPPEDWINDOW**、**WS\_CLIPCHILDREN**と **WS\_CLIPSIBLINGS**。  使用される拡張スタイルは次のとおりです。: **WS\_EX\_APPWINDOW** と **WS\_EX\_WINDOWEDGE**。  
  
 `CMDIChildWinTraits`  
 標準の MDI 子ウィンドウを目的に設計されています。  使用される標準のスタイルは次のとおりです。: **WS\_OVERLAPPEDWINDOW**、**WS\_CHILD**、**WS\_VISIBLE**、**WS\_CLIPCHILDREN**と **WS\_CLIPSIBLINGS**。  使用される拡張スタイルは次のとおりです。: **WS\_EX\_MDICHILD**。  
  
 インスタンスごと、使用 [CWinTraitsOR](../../atl/reference/cwintraitsor-class.md) に設定する他のスタイルの中に特定のスタイルは、ウィンドウ クラスのすべてのインスタンスに設定されるようにする場合は。  
  
## 必要条件  
 **Header:** atlwin.h  
  
## 参照  
 [Class Members](http://msdn.microsoft.com/ja-jp/dbe6a147-3f01-4aea-a3fb-fe6ebadc31f8)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [ウィンドウの特徴について](../../atl/understanding-window-traits.md)