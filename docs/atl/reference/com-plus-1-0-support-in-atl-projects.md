---
title: "ATL プロジェクトでの COM+ 1.0 のサポート | Microsoft Docs"
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
  - "vc.appwiz.ATL.MTS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL プロジェクト, COM+ 1.0 のサポート"
ms.assetid: 51fb08ac-d632-4657-a4e0-d3f989f0b6f8
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL プロジェクトでの COM+ 1.0 のサポート
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[ATL プロジェクト ウィザード](../../atl/reference/creating-an-atl-project.md)を使用して、COM\+ 1.0 コンポーネントの基本的なサポートを含むプロジェクトを作成できます。  
  
 COM\+ 1.0 は、コンポーネント ベースの分散アプリケーションの開発用にデザインされています。  また、COM\+ 1.0 には、これらのアプリケーションを配置および管理するランタイム インフラストラクチャも用意されています。  
  
 \[COM\+ 1.0 のサポート\] チェック ボックスをオンにすると、ウィザードでリンク ステップのビルド スクリプトが変更されます。  具体的には、COM\+ 1.0 プロジェクトが以下のライブラリにリンクされます。  
  
-   comsvcs.lib  
  
-   Mtxguid.lib  
  
 \[COM\+ 1.0 のサポート\] チェック ボックスをオンにした場合は、\[コンポーネント レジスタのサポート\] も選択できます。  コンポーネント レジスタを使用すると、COM\+ 1.0 オブジェクトでコンポーネント リストを取得したり、コンポーネントを登録したり、個別または一度にコンポーネントの登録を解除したりできます。  
  
## 参照  
 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)