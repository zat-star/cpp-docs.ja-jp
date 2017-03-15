---
title: "ActiveX コントロール コンテナー : コントロール コンテナー アプリケーションへのコントロールの追加 | Microsoft Docs"
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
  - "ActiveX コントロール コンテナー [C++], 挿入 (コントロールを)"
  - "ActiveX コントロール [C++], 追加 (プロジェクトに)"
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ActiveX コントロール コンテナー : コントロール コンテナー アプリケーションへのコントロールの追加
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ActiveX コントロール コンテナー アプリケーションから ActiveX コントロールにアクセスする前に [ActiveX コントロールの挿入](../Topic/Insert%20ActiveX%20Control%20Dialog%20Box.md) ダイアログ ボックスを使用して、コンテナー アプリケーションに ActiveX コントロールを追加する必要があります。  
  
 ActiveX コントロール コンテナーのプロジェクトに ActiveX コントロールを追加するには、[ActiveX コントロールを Dialog Box に表示して追加します。](../mfc/viewing-and-adding-activex-controls-to-a-dialog-box.md)を参照してください。  
  
 コントロールを追加すると、ダイアログ ボックスに ActiveX コントロール クラス \(型\) のメンバー変数を追加する必要があります。  この手順の詳細については、「[メンバー変数の追加](../ide/adding-a-member-variable-visual-cpp.md)」を参照してください。  
  
 メンバー変数を追加するラッパー クラスと呼ばれるクラスがプロジェクトに自動的に生成され、追加されます。  このクラスは、コントロール コンテナーと埋め込みコントロール間のインターフェイスとして使用されます。  
  
## 参照  
 [ActiveX コントロール コンテナー](../mfc/activex-control-containers.md)