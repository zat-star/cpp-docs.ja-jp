---
title: "CSettingsStoreSP クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSettingsStoreSP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSettingsStoreSP クラス"
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# CSettingsStoreSP クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CSettingsStoreSP` クラスは、[CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)のインスタンスの作成に使用できるヘルパー クラスです。  
  
## 構文  
  
```  
class CSettingsStoreSP  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSettingsStoreSP::CSettingsStoreSP](../Topic/CSettingsStoreSP::CSettingsStoreSP.md)|`CSettingsStoreSP` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSettingsStoreSP::Create](../Topic/CSettingsStoreSP::Create.md)|`CSettingsStore` から派生したクラスのインスタンスを作成します。|  
|[CSettingsStoreSP::SetRuntimeClass](../Topic/CSettingsStoreSP::SetRuntimeClass.md)|ランタイム クラスを設定します。  `Create` メソッドは、このランタイム クラスを使用して、作成するオブジェクトのクラスを決定します。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|`m_dwUserData`|`CSettingsStoreSP` オブジェクトに格納されるカスタム ユーザー データ。  このデータを `CSettingsStoreSP` オブジェクトのコンストラクターに渡します。|  
|`m_pRegistry`|`Create` メソッドが作成する `CSettingsStore` 派生オブジェクト。|  
  
## 解説  
 `CSettingsStoreSP` クラスを使用すると、すべての MFC レジストリ操作を XML ファイルやデータベースなどの他の場所にリダイレクトできます。  その場合は、次の手順を実行します。  
  
1.  クラス \(`CMyStore` など\) を作成し、`CSettingsStore` から派生させます。  
  
2.  カスタムの `CSettingsStore` クラスで [DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md) マクロと [IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md) マクロを使用して、動的生成を有効にします。  
  
3.  仮想関数をオーバーライドして、`Read` 関数と `Write` 関数をカスタム クラスに実装します。  所定の場所に対するデータの読み取りや書き込みを行う機能が、他に必要であれば実装します。  
  
4.  アプリケーションで、`CSettingsStoreSP::SetRuntimeClass` を呼び出し、カスタム クラスから取得される [CRuntimeClass 構造体](../Topic/CRuntimeClass%20Structure.md)へのポインターを渡します。  
  
 これにより、フレームワークが標準的な動作としてレジストリにアクセスするたびに、カスタム クラスが動的にインスタンス化され、データの読み取りや書き込みに使用されます。  
  
 `CSettingsStoreSP::SetRuntimeClass` はグローバル静的変数を使用します。  このため、一度に使用できるカスタム ストアは 1 つだけです。  
  
## 必要条件  
 **ヘッダー :** afxsettingsstore.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CSettingsStore クラス](../../mfc/reference/csettingsstore-class.md)