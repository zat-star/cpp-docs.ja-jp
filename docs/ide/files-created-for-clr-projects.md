---
title: "CLR プロジェクト用に作成されるファイル | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - ".NET アプリケーション, C++"
  - "Visual C++ プロジェクト, CLR プログラミング"
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CLR プロジェクト用に作成されるファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ テンプレートを使用してプロジェクトを作成する場合は、使用するテンプレートに応じて、複数のファイルが作成されます。  次の表は、.NET Framework プロジェクト用のプロジェクト テンプレートによって作成されるすべてのファイルの一覧です。  
  
|ファイル名|ファイルの説明|  
|-----------|-------------|  
|AssemblyInfo.cpp|プロジェクトのアセンブリ メタデータを変更するための情報 \(属性、ファイル、リソース、型、バージョン管理情報、署名情報など\) を格納したファイル。  詳細については、「[アセンブリの内容](../Topic/Assembly%20Contents.md)」を参照してください。|  
|*projname*.asmx|XML Web サービスの機能をカプセル化したマネージ クラスを参照するテキスト ファイル。|  
|*projname*.cpp|Visual Studio で作成されたアプリケーションのエントリ ポイントであるメイン ソース ファイル。  プロジェクトの .dll ファイルと、プロジェクトの名前空間を識別します。  このファイルには、独自のコードを記述します。|  
|*projname*.vsdisco|XML Web サービスを記述するほかのリソースへのリンクを格納した XML 配置ファイル。|  
|*projname*.h|プロジェクトのメイン インクルード ファイル。このファイルには、すべての宣言、グローバル シンボル、およびほかのヘッダー ファイルについての `#include` ディレクティブが格納されます。|  
|*projname*.sln|プロジェクトのすべての要素を 1 つのソリューションに編成するために開発環境で使用するソリューション ファイル。|  
|*projname*.suo|開発環境内で使用するソリューション オプション ファイル。|  
|*projname.vcxproj*|プロジェクト固有の情報を格納する、開発環境で使用するプロジェクト ファイル。|  
|ReadMe.txt|プロジェクト内の各ファイルを、テンプレートで作成された実際のファイル名を使用して説明したファイルです。|