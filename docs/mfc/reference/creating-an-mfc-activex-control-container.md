---
title: "MFC ActiveX コントロール コンテナーの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.activex.container"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX コントロール コンテナー [C++], 作成"
  - "コンテナー [C++], 作成"
  - "MFC ActiveX コントロール [C++], コンテナー"
  - "OLE コントロール [C++], コンテナー"
ms.assetid: ec70e137-7c14-4940-bd0e-fd4edcc63ea5
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# MFC ActiveX コントロール コンテナーの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ActiveX コントロール コンテナーは、ActiveX \(以前の OLE\) コントロールが動作する環境を提供する親プログラムです。  ActiveX コントロールを含むアプリケーションは MFC を使用しなくても作成できますが、MFC を使用した方が簡単です。  
  
 [MFC アプリケーション ウィザード](../Topic/MFC%20Application%20Wizard.md)を使用して MFC コンテナー プログラムを作成すると、MFC と ActiveX のクラスによって実装された ActiveX コントロールとオートメーションの多数の機能にアクセスできます。  これらの機能には、ビジュアル編集、オートメーション、複合ファイルの作成、コントロールのサポートなどがあります。  親プログラムがサポートする MFC アプリケーション ウィザードのビジュアル編集オプションには、コンテナー、ミニ サーバー、フル サーバー、コンテナーとサーバーの両方を兼ねるプログラムの作成などがあります。  
  
-   新しい MFC アプリケーション。  オートメーション、ビジュアル編集、複合ファイル、またはコントロール サポートを含む MFC プログラムを新規作成するには、MFC アプリケーション ウィザードを使用して、適切なオートメーション オプションを選択します。  
  
-   既存の MFC アプリケーション。  既存の MFC アプリケーションにコントロール コンテインメントを追加する場合は、「[ActiveX コントロール コンテナー : ActiveX コントロール サポートの手動による有効化](../Topic/ActiveX%20Control%20Containers:%20Manually%20Enabling%20ActiveX%20Control%20Containment.md)」を参照してください。  
  
### ActiveX コンテナーは、以下のアプリケーションに対して作成できます。  
  
1.  [コンテナー](../../mfc/containers.md)  
  
2.  [ビジュアル編集](../../mfc/ole-mfc.md)  
  
3.  [MFC ActiveX コントロール](../../mfc/mfc-activex-controls.md)  
  
## 参照  
 [Visual C\+\+ プロジェクトの種類](../../ide/visual-cpp-project-types.md)