---
title: "CCachedDataPathProperty クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CCachedDataPathProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール [C++], 非同期"
  - "非同期コントロール [C++]"
  - "CCachedDataPathProperty クラス"
  - "メモリ ファイル [C++]"
  - "OLE コントロール [C++], 非同期"
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CCachedDataPathProperty クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

非同期で転送し、メモリ ファイルにキャッシュする OLE コントロール プロパティを実装します。  
  
## 構文  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](../Topic/CCachedDataPathProperty::CCachedDataPathProperty.md)|`CCachedDataPathProperty` オブジェクトを構築します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CCachedDataPathProperty::m\_Cache](../Topic/CCachedDataPathProperty::m_Cache.md)|データをキャッシュする`CMemFile` のオブジェクト。|  
  
## 解説  
 メモリ ファイルをディスクではなく RAM に格納され、高速一時コピーに便利です。  
  
 **CAysncMonikerFile** と `CDataPathProperty`とともに、`CCachedDataPathProperty` は、OLE コントロールの非同期モニカーを使用して機能を提供します。  `CCachedDataPathProperty` のオブジェクトによって、URL からデータを非同期的にシフトし、ソース ファイルを、`m_Cache` のパブリック変数によってメモリ ファイルに格納されます。  すべてのデータはメモリのファイルに格納され、通知のかを確認し、応答するには [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md) をオーバーライドする必要はありません。  より多くのデータを受信したとき、それ自体を再描画する必要があります。たとえば、大きな .gif ファイルを転送、コントロールに通知する場合は、通知をオーバーライドする `OnDataAvailable`。  
  
 クラス `CCachedDataPathProperty` は `CDataPathProperty`から派生します。  
  
 インターネット アプリケーションで非同期モニカーと ActiveX コントロールを使用する方法の詳細については、次のトピックを参照:  
  
-   [インターネットの対処方法: &#91;ActiveX コントロール&#93;](../../mfc/activex-controls-on-the-internet.md)  
  
-   [インターネットの対処方法: 非同期モニカー](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../Topic/COleStreamFile%20Class.md)  
  
 [CMonikerFile](../Topic/CMonikerFile%20Class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)  
  
 `CCachedDataPathProperty`  
  
## 必要条件  
 **Header:** afxctl.h  
  
## 参照  
 [CDataPathProperty クラス](../../mfc/reference/cdatapathproperty-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDataPathProperty クラス](../../mfc/reference/cdatapathproperty-class.md)