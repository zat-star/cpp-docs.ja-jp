---
title: "CLR プロジェクト用に作成されるファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++ projects, CLR programming
- .NET applications, C++
ms.assetid: 59ae9020-5f26-4ad0-bbdd-97c2e2023a20
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4abf5415e9b252a7cc92408fb273d226106fc16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="files-created-for-clr-projects"></a>CLR プロジェクト用に作成されるファイル
Visual C のテンプレートを使用して、プロジェクトを作成するときに、使用するテンプレートによって、いくつかのファイルが作成されます。 次の表は、.NET Framework プロジェクトのプロジェクト テンプレートによって作成されるすべてのファイルを一覧表示します。  
  
|ファイル名|ファイルの説明|  
|---------------|----------------------|  
|AssemblyInfo.cpp|プロジェクトのアセンブリ メタデータの変更の情報 (つまり、属性、ファイル、リソース、型、バージョン管理情報、署名情報、およびなど) が含まれるファイル。 詳細については、次を参照してください。[アセンブリ概念](/dotnet/framework/app-domains/assembly-contents)です。|  
|*projname*.asmx|マネージ XML Web サービスの機能をカプセル化するクラスを参照するテキスト ファイルです。|  
|*projname*.cpp|メインのソース ファイルとエントリは、アプリケーションに自動的に作成する Visual Studio をポイントします。 プロジェクトの .dll ファイルと、プロジェクトの名前空間を識別します。 このファイルには、独自のコードを記述します。|  
|*projname*.vsdisco|XML Web サービスを記述する他のリソースへのリンクを含む XML 展開ファイル。|  
|*projname*.h|すべての宣言、グローバル シンボルを含むプロジェクトのメインのインクルード ファイルと`#include`他のヘッダー ファイルのディレクティブ。|  
|*projname*.sln|開発環境で 1 つのソリューション、プロジェクトのすべての要素を整理するために使用するソリューション ファイルです。|  
|*projname*.suo|開発環境で使用されるソリューション オプション ファイルです。|  
|*projname*.vcxproj|このプロジェクトに固有の情報を格納する開発環境で使用されるプロジェクト ファイルです。|  
|ReadMe.txt|テンプレートによって作成された実際のファイル名を使用して、プロジェクト内の各ファイルを記述するファイルです。|