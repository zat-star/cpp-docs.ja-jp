---
title: "CWindowImpl によるウィンドウの実装 | Microsoft Docs"
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
  - "CWindowImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, ウィンドウ"
  - "サブクラス化 (ATL ウィンドウ クラスを)"
  - "スーパークラス化, ATL"
  - "ウィンドウ [C++], ATL"
  - "ウィンドウ [C++], サブクラス化"
  - "ウィンドウ [C++], スーパークラス化"
ms.assetid: 3fc40550-f1d6-4702-8b7c-4cf682b6a855
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWindowImpl によるウィンドウの実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ウィンドウを実行するには、`CWindowImpl`からクラスを派生します。  、派生クラスでは、メッセージ マップとメッセージ ハンドラー関数を宣言します。  3 種類の方法で、クラスを使用する:  
  
-   [新しいウィンドウ クラスに基づいてウィンドウを作成します。](#_atl_creating_a_window_based_on_a_new_windows_class)  
  
-   [スーパークラス Windows の既存のクラス](#_atl_superclassing_an_existing_windows_class)  
  
-   [サブクラス既存のウィンドウ](#_atl_subclassing_an_existing_window)  
  
##  <a name="_atl_creating_a_window_based_on_a_new_windows_class"></a> 新しいウィンドウ クラスに基づくウィンドウを作成します  
 `CWindowImpl` は、Windows のクラス情報を宣言するに [DECLARE\_WND\_CLASS](../Topic/DECLARE_WND_CLASS.md) のマクロが含まれています。  このマクロは、新しいウィンドウ クラス情報を定義するに [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) を使用する `GetWndClassInfo` 関数を実装します。  `CWindowImpl::Create` が呼び出されると、Windows のこのクラスは、登録され、新しいウィンドウが作成されます。  
  
> [!NOTE]
>  `CWindowImpl` では、`DECLARE_WND_CLASS` の ATL マクロには、Windows のクラス名を生成することを **NULL** を渡します。  独自の名前を指定するには、の `CWindowImpl`の `DECLARE_WND_CLASS` に文字列\-派生クラスを渡します。  
  
## 使用例  
 次に、新しいウィンドウ クラスに基づいてウィンドウを実装するクラスの例です:  
  
 [!code-cpp[NVC_ATL_Windowing#64](../atl/codesnippet/CPP/implementing-a-window-with-cwindowimpl_1.h)]  
  
 ウィンドウを作成するには、`CMyWindow` のインスタンスを作成し、**\[作成\]** のメソッドを呼び出します。  
  
> [!NOTE]
>  既定のウィンドウ クラス情報をオーバーライドするには、適切な値へ `CWndClassInfo` のメンバーを設定することによって、派生クラスの `GetWndClassInfo` のメソッドを実装します。  
  
##  <a name="_atl_superclassing_an_existing_windows_class"></a> Windows の既存のクラスのスーパークラス化  
 [DECLARE\_WND\_SUPERCLASS](../Topic/DECLARE_WND_SUPERCLASS.md) のマクロは、スーパークラス Windows の既存のウィンドウ クラスを作成することができます。  このマクロで `CWindowImpl`、の派生クラスを指定します。  他の ATL ウィンドウと同様に、メッセージは、メッセージ マップによって処理されます。  
  
 `DECLARE_WND_SUPERCLASS`を使用すると、新しいウィンドウ クラスは登録されます。  この新しいクラスは、既存のクラスを `CWindowImpl::WindowProc` と指定し、ウィンドウ プロシージャを置き換える同じです \(またはこのメソッドをオーバーライドする\) と、関数。  
  
## 使用例  
 以下は、標準エディット コントロールをスーパークラス化するクラスの例です:  
  
 [!code-cpp[NVC_ATL_Windowing#65](../atl/codesnippet/CPP/implementing-a-window-with-cwindowimpl_2.h)]  
  
 スーパークラス化された編集ウィンドウを作成するには、`CMyEdit` のインスタンスを作成し、**\[作成\]** のメソッドを呼び出します。  
  
##  <a name="_atl_subclassing_an_existing_window"></a> 既存のウィンドウのサブクラス化  
 サブクラスに既存のウィンドウは `CWindowImpl` からクラスを派生し、2 種類の前の場合のようにメッセージ マップを宣言します。  ただし、サブクラス既存のウィンドウため、Windows のクラス情報を指定していないので注意してください。  
  
 **\[作成\]**を呼び出す代わりに、`SubclassWindow` を呼び出して、サブクラスにするには、既存のウィンドウ ハンドルを渡します。  ウィンドウがサブクラス化、`CWindowImpl::WindowProc` \(またはこのメソッドをオーバーライドするメッセージ マップにメッセージを指示するには、関数を使用します。  、オブジェクトからサブクラス化されたウィンドウをデタッチするには、`UnsubclassWindow`を呼び出します。  ウィンドウの元のウィンドウ プロシージャは、復元されます。  
  
## 参照  
 [ウィンドウの実装](../atl/implementing-a-window.md)