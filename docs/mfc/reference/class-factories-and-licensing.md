---
title: "クラス ファクトリとライセンス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス ファクトリ, およびライセンス"
ms.assetid: 53c4856a-4062-46db-9f69-dd4339f746b3
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# クラス ファクトリとライセンス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE コントロールのインスタンスを作成するには、コンテナー アプリケーションはコントロールのクラス ファクトリのメンバー関数を呼び出します。  コントロールが実際の OLE オブジェクトであるため、クラス ファクトリはコントロールのインスタンスを作成する必要があります。  すべての OLE コントロール クラスはクラス ファクトリが必要です。  
  
 OLE コントロールのもう一つの重要な機能は、ライセンスを適用する機能です。  ControlWizard コントロールは、プロジェクトの作成時に検証を組み込むことができます。  検証するコントロールの詳細については [ActiveX コントロール: ActiveX コントロールのライセンス](../../mfc/mfc-activex-controls-licensing-an-activex-control.md)記事を参照します。  
  
 次の表は、コントロールのライセンスにコントロール クラス ファクトリと宣言し、実装するために使用されるいくつかの関数とマクロの一覧です。  
  
### クラス ファクトリとライセンス  
  
|||  
|-|-|  
|[DECLARE\_OLECREATE\_EX](../Topic/DECLARE_OLECREATE_EX.md)|OLE コントロールまたはプロパティ ページのクラス ファクトリを宣言します。|  
|[IMPLEMENT\_OLECREATE\_EX](../Topic/IMPLEMENT_OLECREATE_EX.md)|コントロールの `GetClassID` 関数を実装し、ファクトリ クラスのインスタンスを宣言します。|  
|[BEGIN\_OLEFACTORY](../Topic/BEGIN_OLEFACTORY.md)|すべての検証関数の宣言を開始します。|  
|[END\_OLEFACTORY](../Topic/END_OLEFACTORY.md)|すべての検証関数の宣言を終了します。|  
|[AfxVerifyLicFile](../Topic/AfxVerifyLicFile.md)|コントロールが特定のコンピューターで使用するために検証するかどうかを確認します。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)