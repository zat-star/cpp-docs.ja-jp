---
title: "DLL の種類 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "DLL [C++], 種類"
  - "MFC DLL [C++], 種類"
ms.assetid: f6a30db9-6138-4b2c-90cc-a17855e499a6
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# DLL の種類
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここで説明する情報は、ビルドする DLL の種類を決定するときの参考になります。  
  
##  <a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a> 利用できる DLL の種類  
 Visual C\+\+ を使うと、C または C\+\+ で MFC ライブラリを使わない Win32 DLL をビルドできます。  Win32 アプリケーション ウィザードでは、非 MFC DLL プロジェクトを作成できます。  
  
 MFC DLL ウィザードでは、スタティック リンク ライブラリでも、多くの DLL でも、MFC ライブラリ自体を利用できます。  MFC を利用する DLL は、Visual C\+\+ では次の 3 とおりの方法で開発できます。  
  
-   MFC と静的にリンクするレギュラー DLL をビルド  
  
-   MFC と動的にリンクするレギュラー DLL をビルド  
  
-   常に MFC と動的にリンクする MFC 拡張 DLLをビルド  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [非 MFC DLL: 概要](../Topic/Non-MFC%20DLLs:%20Overview.md)  
  
-   [MFC と静的にリンクされるレギュラー DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [MFC と動的にリンクされるレギュラー DLL](../Topic/Regular%20DLLs%20Dynamically%20Linked%20to%20MFC.md)  
  
-   [拡張 DLL : 概要](../build/extension-dlls-overview.md)  
  
-   [使用する DLL の決定](#_core_which_kind_of_dll_to_use)  
  
##  <a name="_core_which_kind_of_dll_to_use"></a> 使用する DLL の決定  
 DLL で MFC を使用しない場合、Visual C\+\+ を使って非 MFC Win32 DLL をビルドします。  リンクの形態が静的か動的かにかかわらず、MFC とリンクする DLL は、ディスク領域とメモリをかなり使用します。  実際に MFC を使わない DLL は、MFC とリンクしないでください。  
  
 MFC または非 MFC アプリケーションから MFC を使用する DLL を使用する場合には、MFC と動的、または静的にリンクされるレギュラー DLL をビルドする必要があります。  DLL のファイル サイズが大幅に小さくなる点、および MFC の共有バージョンを使用することによってメモリを大幅に節約できる点から、ほとんどの場合には、MFC と動的にリンクされるレギュラー DLL を使用します。  MFC と静的にリンクする場合は、MFC ライブラリ コードの専用コピーを読み込むために、DLL のファイル サイズは大きくなり、余分なメモリを使用する可能性があります。  
  
 動的リンクの場合には MFC 自体をリンクする必要がないため、ビルド処理は静的にリンクされる DLL よりも動的にリンクされる DLL の方が高速です。  この傾向は、リンカーがデバッグ情報を圧縮する必要があるデバッグ ビルドについて特に顕著になります。  デバッグ情報を既に含む DLL とリンクすることによって、DLL 内に圧縮されるデバッグ情報が少なくなります。  
  
 MFC との動的リンクの欠点として、MFCx0.dll と Msvcrxx.dll \(または同様のファイル\) という共有 DLL を一緒に配布する必要性が生じる点を挙げることができます。  MFC DLL の再配布は自由ですが、セットアップ プログラムで DLL をインストールする必要があります。  さらに、プログラムと MFC DLL 自体の双方が使用する C ランタイム ライブラリを含む Msvcrxx.dll も同梱する必要があります。  
  
 DLL が MFC の実行形式からのみ使用される場合、レギュラー DLL と拡張 DLL のいずれかをビルドします。  既存の MFC クラスから派生した再利用可能なクラスを DLL に実装する場合、または、MFC からの派生オブジェクトをアプリケーションと DLL の間で受け渡す場合は、拡張 DLL をビルドする必要があります。  
  
 MFC と動的にリンクされる DLL では、DLL と共に MFC DLL を再配布することもあります。  このアーキテクチャでは、使用ディスク領域が抑制され、メモリの使用も最小化されるため、複数の実行可能ファイル間でクラス ライブラリを共有する場合に特に便利です。  
  
 バージョン 4.0 までは、Visual C\+\+ は MFC を使う DLL として、USRDLL と AFXDLL の 2 種類しかサポートしていませんでした。  MFC と静的にリンクされるレギュラー DLL は、これまでの USRDLL と同じ性質を持っています。  MFC 拡張 DLL は、これまでの AFXDLL と同じ性質を持っています。  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [非 MFC DLL: 概要](../Topic/Non-MFC%20DLLs:%20Overview.md)  
  
-   [MFC と静的にリンクされるレギュラー DLL](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [MFC と動的にリンクされるレギュラー DLL](../Topic/Regular%20DLLs%20Dynamically%20Linked%20to%20MFC.md)  
  
-   [拡張 DLL : 概要](../build/extension-dlls-overview.md)  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)