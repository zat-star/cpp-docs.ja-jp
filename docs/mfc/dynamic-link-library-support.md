---
title: "ダイナミック リンク ライブラリのサポート | Microsoft Docs"
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
  - "DLL [C++], MFC"
  - "MFC DLL [C++], 標準 DLL"
  - "NAFXDW.LIB"
  - "NAFXDWD.LIB"
  - "標準 DLL [C++], プロジェクト ターゲット (DLL として)"
  - "USRDLL, DLL サポート"
ms.assetid: cc31c69f-3c78-4db1-9ecd-0fd8dc3217e3
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ダイナミック リンク ライブラリのサポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NAFXCW.lib と NAFXCWD.lib ライブラリ \(スタティック リンク ライブラリの名前付け規則に [ライブラリの名前付け規則](../Topic/Library%20Naming%20Conventions.md)の表を示す\) クラス ライブラリでビルドされていないアプリケーションで使用できる「レギュラー DLL」と呼ばれるダイナミック リンク ライブラリとしてプロジェクトを作成します \(以前の「USRDLL」\)。  この DLL サポートは DLL に全体のクラス ライブラリを含む MFCx0D.DLL \(AFXDLL と呼ばれます\) でない場合、MFCx0.DLL と同じです。  詳細については、[DLLs](../build/dlls-in-visual-cpp.md) を参照してください。  DLL 名の一覧については、[MFC DLL の名前付け規則](../build/naming-conventions-for-mfc-dlls.md)を参照してください。  
  
## 参照  
 [MFC ライブラリのバージョン](../mfc/mfc-library-versions.md)