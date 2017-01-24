---
title: "C++/CLI 移行ガイド | Microsoft Docs"
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
  - "C++/CLI Version 2"
  - "C++/CLI Version 2, マネージ拡張"
  - "C++ マネージ拡張, アップグレード (構文を)"
  - "移行 [C++], C++/CLI Version 2"
  - "アップグレード (Visual C++ アプリケーションの), C++ のマネージ拡張を Visual C++ 2005 構文に"
ms.assetid: 8ec926b5-73f6-4f0c-bcdf-5203d293849a
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++/CLI 移行ガイド
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

これは、Visual C\+\+ プログラムを C\+\+ マネージ拡張から [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] に移行するためのガイドです。  構文の変更の概要については、「[\(NOTINBUILD\)Managed Extensions for C\+\+ Syntax Upgrade Checklist](http://msdn.microsoft.com/ja-jp/edbded88-7ef3-4757-bd9d-b8f48ac2aada)」を参照してください。  
  
 C\+\+\/CLI は ISO\-C\+\+ 標準言語に対する動的コンポーネント プログラミング パラダイムを拡張します。  新しい言語では、マネージ拡張を強化するさまざまな改良が施されました。  このセクションでは C\+\+ マネージ拡張言語の機能を列挙し、それらの機能の [!INCLUDE[cpp_current_long](../Token/cpp_current_long_md.md)] への割り当てが存在する場合はそれを示します。また、割り当てが存在しない構造体はどれかも説明します。  
  
## このセクションの内容  
 [変更の概略 \(C\+\+\/CLI\)](../dotnet/outline-of-changes-cpp-cli.md)  
 変更を 5 つのカテゴリに分類してわかりやすくまとめた、クイック リファレンスです。  
  
 [言語キーワード \(C\+\+\/CLI\)\]](../Topic/Language%20Keywords%20\(C++-CLI\).md)  
 言語キーワードの変更 \(二重のアンダースコアの廃止やコンテキスト キーワードとスペース区切りキーワードの導入など\) について説明します。  
  
 [マネージ型 \(C\+\+\/CL\)](../dotnet/managed-types-cpp-cl.md)  
 共通型システム \(CTS: Common Type System\) の宣言の構文の変更について確認します。クラス、配列 \(パラメーター配列を含みます\)、列挙型などの宣言の変更について見ていきます。  
  
 [クラスまたはインターフェイス内でのメンバー宣言 \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)  
 スカラー プロパティ、インデックス プロパティ、演算子、デリゲート、イベントなどのクラス メンバーに関連する変更について説明します。  
  
 [値型とその動作 \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 値型、および内部ポインターと固定ポインターの新しいファミリについて説明します。  また、暗黙的なボックス化の導入、ボックス化された値型の不変性、値クラス内の既定のコンストラクターに対するサポートの廃止など、重要なセマンティクスの変更についても解説します。  
  
 [言語の変更の概要](../Topic/General%20Language%20Changes%20\(C++-CLI\).md)  
 キャスト表記のサポート、リテラル文字列の動作などのセマンティクスの変更、および ISO\-C\+\+ と C\+\+\/CLI とのセマンティクスの相違について詳しく紹介します。  
  
## 参照  
 [混在 \(ネイティブおよびマネージ\) アセンブリ](../Topic/Mixed%20\(Native%20and%20Managed\)%20Assemblies.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)