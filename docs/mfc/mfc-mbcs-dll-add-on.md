---
title: "MFC MBCS DLL アドオン | Microsoft Docs"
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
  - "MBCS"
  - "MFC"
ms.assetid: bebec0ff-e019-42ca-b5df-8c218ac5b54a
caps.latest.revision: 17
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC MBCS DLL アドオン
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual Studio 2015 では、マルチバイト文字エンコード \(MBCS\) に対応した MFC ライブラリが、Visual C\+\+ セットアップ コンポーネントに含まれています。 Visual C\+\+ と MFC は、Visual Studio セットアップではオプションのインストール構成です。 MFC が確実にインストールされるようにするには、セットアップで **［カスタム］** を選択して、**［プログラミング言語］** で **［Visual C\+\+］** と **［Microsoft Foundation Classes for C\+\+］** が選択されていることを確認します。 既に Visual Studio がインストールされている場合は、MFC プロジェクトを作成しようとしたときに、Visual C\+\+ や MFC のインストールを促すプロンプトが表示されます。  
  
 **［文字セット］** プロパティを **［マルチ バイト文字セットを使用する］** または **［設定なし］** に設定している、Visual Studio 2015 の MFC プロジェクトをビルドするには、マルチバイト DLL が必要になります。  
  
## 参照  
 [MFC ライブラリのバージョン](../mfc/mfc-library-versions.md)