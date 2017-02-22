---
title: "MFC アプリケーションのローカライズされたリソース: サテライト DLL | Microsoft Docs"
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
  - "DLL [C++], ローカライズ (MFC を)"
  - "ローカリゼーション [C++], MFC リソース"
  - "ローカライズされたリソース [C++]"
  - "MFC DLL [C++], ローカライズ"
  - "複数言語のサポート [C++]"
  - "リソース専用 DLL [C++]"
  - "リソース専用 DLL [C++], MFC アプリケーション"
  - "リソース [MFC], ローカライズ"
  - "サテライト DLL [C++]"
ms.assetid: 3a1100ae-a9c8-47b5-adbd-cbedef5992ef
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# MFC アプリケーションのローカライズされたリソース: サテライト DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC Version 7.0 以降では、複数の言語にローカライズされるアプリケーションの作成に役立つサテライト DLL のサポートが強化されています。  サテライト DLL は、[リソースのみの DLL](../build/creating-a-resource-only-dll.md) であり、特定の言語にローカライズされたアプリケーションのリソースが含まれています。  アプリケーションの実行を開始すると、その環境に最適なローカライズ済みリソースが MFC によって自動的に読み込まれます。  たとえば、英語のリソースを持つアプリケーションに、フランス語とドイツ語のリソースが含まれる 2 つのサテライト DLL を指定できます。  アプリケーションを英語のシステムで実行するときは、英語のリソースが使われます。  アプリケーションをフランス語のシステムで実行するとフランス語のリソースが使われ、ドイツ語のシステムの場合はドイツ語のリソースが使われます。  
  
 MFC アプリケーションのローカライズ済みリソースをサポートするために、MFC では特定の言語にローカライズされたリソースを持つサテライト DLL の読み込みを試みます。  サテライト DLL には、*ApplicationNameXXX*.dll という名前が付けられています。*ApplicationName* は MFC を使用する .exe または .dll の名前であり、*XXX* は ENU や DEU などの 3 文字で表したリソースの言語コードです。  
  
 MFC は、以下の順番で各言語のリソース DLL の読み込みを試み、該当するリソースが見つかると停止します。  
  
1.  \(Windows 2000 以降のみ\) 現在のユーザーの既定の UI 言語。GetUserDefaultUILanguage\(\) Win32 API から返される値と同じです。  
  
2.  \(Windows 2000 以降のみ\) サブ言語が指定されていない現在のユーザーの既定の UI 言語。つまり、ENC \(カナダの英語\) は ENU \(アメリカの英語\)   になります。  
  
3.  システムの既定の UI 言語。  Windows 2000 以降の場合は、GetSystemDefaultUILanguage\(\) API から返される値です。  その他のプラットフォームの場合は、OS の言語です。  
  
4.  サブ言語が指定されていないシステムの既定の UI 言語。  
  
5.  3 文字で表したコード LOC を持つ見せかけの言語。  
  
 サテライト DLL が見つからない場合、MFC ではアプリケーションに含まれているリソースを使用します。  
  
 たとえば、MFC を使用するアプリケーション LangExample.exe が Windows 2000 の複数ユーザー インターフェイス システムで動作していて、システムの UI 言語は ENU \(アメリカの英語\) で、現在のユーザーの UI 言語が   FRC \(カナダのフランス語\) に設定されているとします。  MFC は、次の順番で DLL を検索します。  
  
1.  LangExampleFRC.dll \(ユーザーの UI 言語\)  
  
2.  LangExampleFRA.dll \(サブ言語のないユーザーの UI 言語。この例では、\(フランスの\) フランス語です\)。  
  
3.  LangExampleENU.dll \(システムの UI 言語\)  
  
4.  LangExampleLOC.dll  
  
 これらの DLL がどれも見つからない場合、MFC は LangExample.exe のリソースを使用します。  
  
## 参照  
 [Visual C\+\+ の DLL](../build/dlls-in-visual-cpp.md)   
 [テクニカル ノート 57: MFC コンポーネントのローカライズ](../mfc/tn057-localization-of-mfc-components.md)