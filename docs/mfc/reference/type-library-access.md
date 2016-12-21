---
title: "タイプ ライブラリ アクセス | Microsoft Docs"
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
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "タイプ ライブラリ, アクセス"
ms.assetid: a03fa7f0-86c2-4119-bf81-202916fb74b3
caps.latest.revision: 14
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# タイプ ライブラリ アクセス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

タイプ ライブラリは、OLE コントロールのインターフェイスを、OLE を認識できるほかのアプリケーションに公開します。  1 つ以上のインターフェイスを公開するときは、各 OLE コントロールがタイプ ライブラリを持つ必要があります。  
  
 OLE コントロールが、それ自体が持つタイプ ライブラリにアクセスできるようにするマクロを次に示します。  
  
### タイプ ライブラリ アクセス  
  
|||  
|-|-|  
|[DECLARE\_OLETYPELIB](../Topic/DECLARE_OLETYPELIB.md)|OLE コントロールの `GetTypeLib` メンバー関数を宣言します。クラスの宣言の中で使用する必要があります。|  
|[IMPLEMENT\_OLETYPELIB](../Topic/IMPLEMENT_OLETYPELIB.md)|OLE コントロールの `GetTypeLib` メンバー関数を実装します。クラスの実装の中で使用する必要があります。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)