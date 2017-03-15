---
title: "方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.howto.addcustombuildtools"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "msbuild (c++), 方法: カスタム ビルド ツールを追加する"
ms.assetid: de03899a-371d-4396-9bf9-34f45a65e909
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

カスタム ビルド ツールは、特定のファイルに関連付けられているユーザー定義のコマンド ライン ツールです。  
  
 特定のファイルに対して、実行するコマンド ライン、追加の入力または出力ファイル、および表示するメッセージをプロジェクト ファイル \(.vcxproj\) で指定します。  **MSBuild** は、入力ファイルに対して出力ファイルが最新でないと判断すると、メッセージを表示し、コマンドを実行します。  
  
 カスタム ビルド ツールをいつ実行するかを指定するには、プロジェクト ファイルで `CustomBuildBeforeTargets` と `CustomBuildAfterTargets` という XML 要素のいずれかまたは両方を使用します。  たとえば、MIDL コンパイラの後、かつ C\/C\+\+ コンパイラの前にカスタム ビルド ツールを実行するように指定できます。  ツールを特定のターゲットを実行する前に実行するには、`CustomBuildBeforeTargets` 要素を指定し、特定のターゲットを実行した後で実行するには `CustomBuildAfterTargets` 要素を指定します。また、ツールを 2 つのターゲットの間で実行するには、両方の要素を指定します。  どちらの要素も指定しない場合、カスタム ビルド ツールは既定の場所 \(**MIDL** ターゲットを実行する前\) で実行されます。  
  
 カスタム ビルド ステップとカスタム ビルド ツールは、`CustomBuildBeforeTargets` XML 要素と `CustomBuildAfterTargets` XML 要素で指定された情報を共有します。  プロジェクト ファイルでは、これらのターゲットは 1 回だけ指定します。  
  
### カスタム ビルド ツールを追加するには  
  
1.  項目グループをプロジェクト ファイルに追加し、それぞれの入力ファイルに項目を追加します。  ここに示すように、コマンド、追加の入力と出力、およびメッセージを項目メタデータとして指定します。  この例は、"faq.txt" という名前のファイルがプロジェクトと同じディレクトリに存在していることを前提としています。  
  
    ```  
    <ItemGroup>  
      <CustomBuild Include="faq.txt">  
        <Message>Copying readme...</Message>  
        <Command>copy %(Identity) $(OutDir)%(Identity)</Command>  
        <Outputs>$(OutDir)%(Identity)</Outputs>  
      </CustomBuild>  
    </ItemGroup>  
    ```  
  
### カスタム ビルド ツールを実行するビルド内の場所を定義するには  
  
1.  次のプロパティ グループをプロジェクト ファイルに追加します。  少なくとも 1 つのターゲットを指定する必要がありますが、ビルド ステップを特定のターゲットの前または後にのみ実行する場合は、もう 1 つのターゲットを省略できます。  この例は、コンパイルの後、かつリンクの前にカスタム ステップを実行します。  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## 参照  
 [チュートリアル: MSBuild を使用した Visual C\+\+ プロジェクトの作成](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [方法: MSBuild プロジェクトでビルド イベントを使用する](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する](../Topic/How%20to:%20Add%20a%20Custom%20Build%20Step%20to%20MSBuild%20Projects.md)