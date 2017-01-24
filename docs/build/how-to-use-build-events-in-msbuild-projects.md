---
title: "方法: MSBuild プロジェクトでビルド イベントを使用する | Microsoft Docs"
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
  - "msbuild.cpp.howto.usebuildevents"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "msbuild (c++), 方法: プロジェクトでビルド イベントを使用する"
ms.assetid: 2a58dc9d-3d50-4e49-97c1-86c5a05ce218
caps.latest.revision: 23
caps.handback.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 方法: MSBuild プロジェクトでビルド イベントを使用する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ビルド イベントは、ビルド処理の特定のステージで [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] を実行するコマンドです。  *ビルド前のイベントは*、ビルドの開始前に発生する; *リンク前* イベントは、リンク ステップの開始前に発生する; *ビルド イベントは*、ビルドが正常に完了した後に発生します。  ビルド イベントは、関連付けられているビルド ステップを実行するときにのみ発生します。  たとえば、リンク前イベントは、リンク ステップが実行されない場合には発生しません。  
  
 項目定義グループでは、これらの 3 つのビルド イベントは、**MSBuild** がビルド イベントを実行するときに実行されるコマンド要素 \(`<Command>`\) および表示されるメッセージ要素 \(`<Message>`\) で表されます。  それぞれの要素は省略可能で、同じ要素を複数回指定すると、最後の指定が優先されます。  
  
 省略可能な *ビルドで使用* 要素 \(`<`*build\-event***UseInBuild**`>`\) は、プロパティ グループでビルド イベントが実行されるかどうかを指定できます。  *ビルドで使用*要素のコンテンツの値は、`true` または `false` です。  既定では、ビルド イベントに対応する*ビルドで使用*要素が `false` に設定されていない限り、そのビルド イベントは実行されます。  
  
 次の表は、ビルド イベント XML 要素の一覧です。  
  
|XML 要素|説明|  
|------------|--------|  
|`PreBuildEvent`|このイベントは、ビルドの開始前に実行します。|  
|`PreLinkEvent`|このイベントは、リンク ステップの開始前に実行します。|  
|`PostBuildEvent`|このイベントは、ビルドの完了後に実行します。|  
  
 次の表は、*ビルドで使用*要素の一覧です。  
  
|XML 要素|説明|  
|------------|--------|  
|`PreBuildEventUseInBuild`|*ビルド前*イベントを実行するかどうかを指定します。|  
|`PreLinkEventUseInBuild`|*リンク前*イベントを実行するかどうかを指定します。|  
|`PostBuildEventUseInBuild`|*ビルド後*イベントを実行するかどうかを指定します。|  
  
## 使用例  
 次の例は、「[チュートリアル: MSBuild を使用した Visual C\+\+ プロジェクトの作成](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)」で作成した myproject.vcxproj ファイルの Project 要素内に追加できます。  *ビルド前*イベントは、main.cpp のコピーを作成します。*リンク前*イベントは、main.obj のコピーを作成します。*ビルド後*イベントは、myproject.exe のコピーを作成します。  プロジェクトがリリース構成を使用してビルドされている場合、ビルド イベントは実行されます。  プロジェクトがデバッグ構成を使用してビルドされている場合、ビルド イベントは実行されません。  
  
```  
<ItemDefinitionGroup>  
  <PreBuildEvent>  
    <Command>copy $(ProjectDir)main.cpp $(ProjectDir)copyOfMain.cpp</Command>  
    <Message>Making a copy of main.cpp </Message>  
  </PreBuildEvent>  
  <PreLinkEvent>  
 <Command>copy $(ProjectDir)$(Configuration)\main.obj $(ProjectDir)$(Configuration)\copyOfMain.obj</Command>  
    <Message>Making a copy of main.obj</Message>  
  </PreLinkEvent>  
  <PostBuildEvent>  
 <Command>copy $(ProjectDir)$(Configuration)\$(TargetFileName) $(ProjectDir)$(Configuration)\copyOfMyproject.exe</Command>  
    <Message>Making a copy of myproject.exe</Message>  
  </PostBuildEvent>  
</ItemDefinitionGroup>  
  
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">  
  <PreBuildEventUseInBuild>true</PreBuildEventUseInBuild>  
  <PreLinkEventUseInBuild>true</PreLinkEventUseInBuild>  
  <PostBuildEventUseInBuild>true</PostBuildEventUseInBuild>  
</PropertyGroup>  
  
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">  
  <PreBuildEventUseInBuild>false</PreBuildEventUseInBuild>  
  <PreLinkEventUseInBuild>false</PreLinkEventUseInBuild>  
  <PostBuildEventUseInBuild>false</PostBuildEventUseInBuild>  
</PropertyGroup>  
```  
  
## 参照  
 [MSBuild \(Visual C\+\+\)](../Topic/MSBuild%20\(Visual%20C++\).md)   
 [チュートリアル: MSBuild を使用した Visual C\+\+ プロジェクトの作成](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)