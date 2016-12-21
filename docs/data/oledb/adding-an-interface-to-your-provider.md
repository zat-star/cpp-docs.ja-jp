---
title: "プロバイダーへのインターフェイスの追加 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB プロバイダー テンプレート, オブジェクト インターフェイス"
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# プロバイダーへのインターフェイスの追加
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インターフェイスを追加するオブジェクト \(通常は、OLE DB プロバイダー ウィザードによって作成されたデータ ソース、行セット、コマンド、またはセッション オブジェクト\) を決定します。  インターフェイスを追加する必要のあるオブジェクトをプロバイダーがサポートしていない場合があります。  その場合には、ATL OLE DB プロバイダー ウィザードを実行してオブジェクトを作成します。  \[クラス ビュー\] でプロジェクトを右クリックし、\[追加\] メニューの \[クラスの追加\] をクリックし、\[ATL OLE DB プロバイダー\] をクリックします。  別のディレクトリにインターフェイス コードを挿入し、プロバイダー プロジェクトにファイルをコピーできます。  
  
 インターフェイスをサポートするクラスを新規作成してある場合には、そのクラスからオブジェクトを継承させます。  たとえば、次のように **IRowsetIndexImpl** クラスを行セット オブジェクトに追加します。  
  
```  
template <class Creator>  
class CAgentRowset :   
public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
   public IRowsetIndexImpl< ... >   
```  
  
 COM\_INTERFACE\_ENTRY マクロを使用して、オブジェクトの **COM\_MAP** にインターフェイスを追加します。  マップがない場合は、マップを作成します。  たとえば、次のようになります。  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
 行セット オブジェクトの場合には、親オブジェクトのマップをチェインして、オブジェクトが親クラスに処理を代行させることができるようにします。  この例では、COM\_INTERFACE\_ENTRY\_CHAIN マクロをマップに追加します。  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## 参照  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)