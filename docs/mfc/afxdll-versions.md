---
title: "AFXDLL バージョン | Microsoft Docs"
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
  - "afxdll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AFXDLL ライブラリ"
  - "アプリケーション ウィザード [C++], 既定で使用する AFXDLL"
  - "MFC の DLL バージョン [C++]"
  - "MFC [C++], AFXDLL バージョン"
  - "MFC DLL [C++], 動的リンク (ライブラリへの)"
  - "MFC ライブラリ [C++], 動的リンク"
ms.assetid: c078ae8f-85a9-43cb-9ded-c09ca2c45723
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AFXDLL バージョン
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC のオブジェクト コード ライブラリに静的にリンクしてアプリケーションを作成する代わりに、複数の共有実行中のアプリケーションが使用する DLL で MFC を含む AFXDLL ライブラリ 1 を使用するようにアプリケーションをビルドできます。  AFXDLL 名の一覧については、[DLL: 名前付け規則](../build/naming-conventions-for-mfc-dlls.md)を参照してください。  
  
> [!NOTE]
>  既定では、MFC アプリケーション ウィザード AFXDLL のプロジェクトを作成します。  MFC コードの静的なリンクを使用するには、MFC アプリケーション ウィザードの **スタティック ライブラリで MFC を使用する** オプションを設定します。  静的なリンクは、Visual C\+\+ の Standard Edition では使用できません。  
  
## 参照  
 [MFC ライブラリのバージョン](../mfc/mfc-library-versions.md)