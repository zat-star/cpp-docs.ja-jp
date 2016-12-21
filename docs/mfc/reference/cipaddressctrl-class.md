---
title: "CIPAddressCtrl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CIPAddressCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CIPAddressCtrl クラス"
  - "コモン コントロール, Internet Explorer 4.0"
  - "インターネット アドレスのエディット ボックス"
  - "Internet Explorer 4.0 コモン コントロール"
  - "インターネット プロトコル アドレスのボックス"
  - "IP アドレス コントロール"
ms.assetid: 9764d2f4-cb14-4ba8-b799-7f57a55a47c6
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CIPAddressCtrl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Windows コモン IP アドレス コントロールの機能が用意されています。  
  
## 構文  
  
```  
class CIPAddressCtrl : public CWnd  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CIPAddressCtrl::CIPAddressCtrl](../Topic/CIPAddressCtrl::CIPAddressCtrl.md)|`CIPAddressCtrl` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CIPAddressCtrl::ClearAddress](../Topic/CIPAddressCtrl::ClearAddress.md)|IP アドレス コントロールの内容を消去します。|  
|[CIPAddressCtrl::Create](../Topic/CIPAddressCtrl::Create.md)|IP アドレス コントロールを作成し、`CIPAddressCtrl` のオブジェクトにアタッチします。|  
|[CIPAddressCtrl::CreateEx](../Topic/CIPAddressCtrl::CreateEx.md)|指定されたウィンドウの拡張スタイルの IP アドレス コントロールを作成し、`CIPAddressCtrl` のオブジェクトにアタッチします。|  
|[CIPAddressCtrl::GetAddress](../Topic/CIPAddressCtrl::GetAddress.md)|IP アドレス コントロールの 4 つすべてのフィールドのアドレス値を取得します。|  
|[CIPAddressCtrl::IsBlank](../Topic/CIPAddressCtrl::IsBlank.md)|IP アドレス コントロールのすべてのフィールドが空であるかどうかを判定します。|  
|[CIPAddressCtrl::SetAddress](../Topic/CIPAddressCtrl::SetAddress.md)|IP アドレス コントロールの 4 つすべてのフィールドのアドレス値を設定します。|  
|[CIPAddressCtrl::SetFieldFocus](../Topic/CIPAddressCtrl::SetFieldFocus.md)|IP アドレス コントロールのフィールドにキーボード フォーカスを設定します。|  
|[CIPAddressCtrl::SetFieldRange](../Topic/CIPAddressCtrl::SetFieldRange.md)|IP アドレス コントロールの指定したフィールドの範囲を設定します。|  
  
## 解説  
 IP アドレス コントロール、編集コントロールと同様に、コントロールは Internet Protocol \(IP\) の形式で数値アドレスを入力して、操作できるようにします。  
  
 このコントロール \(したがって `CIPAddressCtrl` のクラス\) Microsoft Internet Explorer 4.0 以降の下で実行されるプログラムにのみ使用できます。  また、Windows および Windows NT の将来のバージョンで使用できます。  
  
 IP アドレス コントロールについては、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [IP アドレス コントロール](http://msdn.microsoft.com/library/windows/desktop/bb761372) を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 `CIPAddressCtrl`  
  
## 必要条件  
 **ヘッダー :** afxcmn.h  
  
## 参照  
 [CWnd クラス](../Topic/CWnd%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)