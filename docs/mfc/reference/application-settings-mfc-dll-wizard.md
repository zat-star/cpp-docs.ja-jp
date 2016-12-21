---
title: "[アプリケーションの設定] (MFC DLL ウィザード) | Microsoft Docs"
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
  - "vc.appwiz.mfc.dll.appset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC DLL ウィザード、アプリケーションの設定"
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# [アプリケーションの設定] (MFC DLL ウィザード)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC DLL ウィザードのこのページでは、新しい MFC DLL プロジェクトの基本機能のデザインと追加を行います。  
  
## \[DLL の種類\]  
 作成する DLL の種類を選択します。  
  
 **\[共有 MFC DLL を使用する通常の DLL\]**  
 MFC ライブラリを共有 DLL としてプログラムにリンクする場合は、このオプションを選択します。  このオプションを使用すると、作成した DLL と呼び出し元のアプリケーション間で MFC オブジェクトを共有できません。  プログラムは実行時に MFC ライブラリを呼び出します。  このオプションを使用すると、プログラムが MFC ライブラリを使用する複数の実行可能ファイルで構成される場合に、必要なディスクとメモリの量が削減されます。  Win32 プログラムと MFC プログラムは共に DLL 内の関数を呼び出すことができます。  この種類のプロジェクトを使用する場合は、MFC DLL を再配布する必要があります。  
  
 **\[MFC をスタティックにリンクした通常の DLL\]**  
 プログラムと MFC ライブラリをビルド時に静的にリンクする場合は、このオプションを選択します。  Win32 プログラムと MFC プログラムは共に DLL 内の関数を呼び出すことができます。  このオプションを選択するとプログラムのサイズは大きくなりますが、この種類のプロジェクトでは MFC DLL を再配布する必要がありません。  作成した DLL と呼び出し元のアプリケーション間では MFC オブジェクトを共有できません。  
  
 **\[MFC 拡張 DLL\]**  
 実行時にプログラムから MFC ライブラリを呼び出す場合、および作成した DLL と呼び出し元のアプリケーション間で MFC オブジェクトを共有する場合は、このオプションを選択します。  このオプションを使用すると、プログラムが MFC ライブラリを使用する複数の実行可能ファイルで構成される場合に、必要なディスクとメモリの量が削減されます。  作成した DLL の関数を呼び出すことができるのは、MFC プログラムだけです。  この種類のプロジェクトを使用する場合は、MFC DLL を再配布する必要があります。  
  
## \[追加の機能\]  
 作成する MFC DLL でオートメーションや Windows Sockets をサポートするかどうかを指定します。  
  
 **\[オートメーション\]**  
 \[オートメーション\] を選択すると、ほかのプログラムに実装されたオブジェクトをプログラムで操作できます。  また、\[オートメーション\] を選択することによって、プログラムがほかのオートメーション クライアントに公開されます。  詳細については、「[オートメーション](../../mfc/automation.md)」を参照してください。  
  
 **\[Windows ソケット\]**  
 このオプションを選択すると、プログラムで Windows Socketsがサポートされます。  Windows Sockets を使用すると、TCP\/IP ネットワーク上で通信するプログラムを作成できます。  
  
 Windows Sockets をサポートする MFC DLL を作成すると、[CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md) によってソケットのサポートが初期化され、MFC ヘッダー ファイル StdAfx.h に AfxSock.h がインクルードされます。  
  
## 参照  
 [MFC DLL ウィザード](../../mfc/reference/mfc-dll-wizard.md)   
 [MFC DLL プロジェクトの作成](../../mfc/reference/creating-an-mfc-dll-project.md)