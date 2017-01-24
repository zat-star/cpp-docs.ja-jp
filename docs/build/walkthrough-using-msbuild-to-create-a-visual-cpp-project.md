---
title: "チュートリアル: MSBuild を使用した Visual C++ プロジェクトの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "msbuild.cpp.walkthrough.createproject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "msbuild (c++), チュートリアル: プロジェクトの作成"
ms.assetid: 52350d1c-c373-4868-923c-5e8be6f67adb
caps.latest.revision: 27
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# チュートリアル: MSBuild を使用した Visual C++ プロジェクトの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このチュートリアルでは、[!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] を使用して、コマンド プロンプトで [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] プロジェクトをビルドする方法を説明します。  まず、[!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] コンソール アプリケーション用の C\+\+ ソース ファイルと XML ベースのプロジェクト ファイルを作成する方法を学習します。  次に、プロジェクトをビルドしてから、ビルド処理をカスタマイズする方法を学習します。  
  
 このチュートリアルでは、次の作業について説明します。  
  
-   プロジェクトの C\+\+ ソース ファイルの作成。  
  
-   XML [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] プロジェクト ファイルの作成。  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] を使用したプロジェクトのビルド。  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] を使用したプロジェクトのカスタマイズ。  
  
## 必須コンポーネント  
 このチュートリアルを完了するための要件は次のとおりです。  
  
-   [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)]  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] システムの基本的な知識  
  
## C\+\+ ソース ファイルの作成  
 このチュートリアルでは、ソース ファイルとヘッダー ファイルがあるプロジェクトを作成します。  main.cpp という名前のソース ファイルには、コンソール アプリケーションの main 関数を含めます。  main.h という名前のヘッダー ファイルには、iostream ヘッダー ファイルをインクルードするためのコードを含めます。  これらの C\+\+ ファイルは、[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] またはテキスト エディターを使用して作成できます。  
  
#### プロジェクトの C\+\+ ソース ファイルを作成するには  
  
1.  プロジェクトのディレクトリを作成します。  
  
2.  main.cpp という名前のファイルを作成し、このファイルに次のコードを追加します。  
  
    ```cpp  
    // main.cpp : the application source code.  
    #include <iostream>  
    #include "main.h"  
    int main()  
    {  
       std::cout << "Hello, from MSBuild!\n";  
       return 0;  
    }  
    ```  
  
3.  main.h という名前のファイルを作成し、このファイルに次のコードを追加します。  
  
    ```hlsl  
    // main.h: the application header code.  
    /* Additional source code to include. */  
    ```  
  
## プロジェクト ファイルXML MSBuild プロジェクト ファイルの作成  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] プロジェクト ファイルは、プロジェクトのルート要素 \(\<Project\>\) が含まれる XML ファイルです。  次の例に示すプロジェクトでは、\<Project\> 要素に 7 個の子要素が含まれています。  
  
-   3 個の項目グループ タグ \(\<ItemGroup\>\) によって、プロジェクトの構成とプラットフォーム、ソース ファイル名、およびヘッダー ファイル名が指定されます。  
  
-   3 個のインポート タグ \(\<Import\>\) によって、Microsoft [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] の設定の場所が指定されます。  
  
-   1 個のプロパティ グループ タグ \(\<PropertyGroup\>\) によって、プロジェクト設定が指定されます。  
  
#### MSBuild プロジェクト ファイルを作成するには  
  
1.  テキスト エディターを使用して `myproject.vcxproj` という名前のプロジェクト ファイルを作成し、次のルート \<Project\> 要素を追加します。  次のプロシージャ ステップの要素をルート \<Project\> タグの間に挿入します。  
  
    ```xml  
    <Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
    </Project>  
    ```  
  
2.  次の 2 個の \<ProjectConfiguration\> 子要素を \<ItemGroup\> 要素に追加します。  この子要素は、32 ビットの Windows オペレーティング システムのデバッグおよびリリース構成を指定します。  
  
    ```xml  
    <ItemGroup>  
      <ProjectConfiguration Include="Debug|Win32">  
        <Configuration>Debug</Configuration>  
        <Platform>Win32</Platform>  
      </ProjectConfiguration>  
      <ProjectConfiguration Include="Release|Win32">  
        <Configuration>Release</Configuration>  
        <Platform>Win32</Platform>  
      </ProjectConfiguration>  
    </ItemGroup>  
  
    ```  
  
3.  このプロジェクトの既定の C\+\+ 設定のパスを指定する次の \<Import\/\> 要素を追加します。  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />  
  
    ```  
  
4.  2 個のプロジェクト プロパティを指定する次のプロパティ グループ要素 \(\<PropertyGroup\>\) を追加します。  
  
    ```xml  
    <PropertyGroup>  
      <ConfigurationType>Application</ConfigurationType>  
      <PlatformToolset>v120</PlatformToolset>  
    </PropertyGroup>  
    ```  
  
5.  このプロジェクトの現在の C\+\+ 設定のパスを指定する次の \<Import\/\> 要素を追加します。  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
    ```  
  
6.  次の \<ClCompile\> 子要素を \<ItemGroup\> 要素に追加します。  この子要素は、コンパイルする C\/C\+\+ ソース ファイルの名前を指定します。  
  
    ```xml  
    <ItemGroup>  
      <ClCompile Include="main.cpp" />  
    </ItemGroup>  
    ```  
  
7.  次の \<ClInclude\> 子要素を \<ItemGroup\> 要素に追加します。  この子要素は、C\/C\+\+ ソース ファイルに対応するヘッダー ファイルの名前を指定します。  
  
    ```xml  
    <ItemGroup>  
      <ClInclude Include="main.h" />  
    </ItemGroup>  
    ```  
  
8.  このプロジェクトのターゲットを定義するファイルのパスを指定する次の \<Import\> 要素を追加します。  
  
    ```xml  
    <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />  
  
    ```  
  
### 完成したプロジェクト ファイル  
 次のコードは、前の手順で作成したプロジェクト ファイルのすべての内容です。  
  
```xml  
<Project DefaultTargets="Build" ToolsVersion="12.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <ItemGroup>  
    <ProjectConfiguration Include="Debug|Win32">  
      <Configuration>Debug</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
    <ProjectConfiguration Include="Release|Win32">  
      <Configuration>Release</Configuration>  
      <Platform>Win32</Platform>  
    </ProjectConfiguration>  
  </ItemGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.default.props" />  
  <PropertyGroup>  
    <ConfigurationType>Application</ConfigurationType>  
    <PlatformToolset>v120</PlatformToolset>  
  </PropertyGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />  
  <ItemGroup>  
    <ClCompile Include="main.cpp" />  
  </ItemGroup>  
  <ItemGroup>  
    <ClInclude Include="main.h" />  
  </ItemGroup>  
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Targets" />  
</Project>  
```  
  
## MSBuild を使用したプロジェクトのビルド  
 コマンド プロンプトで次のコマンドを入力して、コンソール アプリケーションをビルドします。  
  
```  
msbuild myproject.vcxproj /p:configuration=debug  
```  
  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] は、出力ファイルのディレクトリを作成し、プロジェクトをコンパイルおよびリンクして Myproject.exe プログラムを生成します。  ビルド処理が完了したら、次のコマンドを使用してアプリケーションを実行します。  
  
```  
myproject  
```  
  
 アプリケーションによって、コンソール ウィンドウに "Hello, from MSBuild\!" と表示されます。  
  
## プロジェクトのカスタマイズ  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] では、定義済みのビルド ターゲットを実行したり、ユーザー定義のプロパティを適用したりできるほか、カスタム ツール、イベント、およびビルド ステップを使用することができます。  このセクションでは、次の作業について説明します。  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] とビルド ターゲットの併用。  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] とビルド プロパティの併用。  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] と 64 ビットのコンパイラおよびツールの併用。  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] と他のツールセットの併用。  
  
-   [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] のカスタマイズの追加。  
  
### MSBuild とビルド ターゲットの併用  
 *ビルド ターゲット*は、ビルド時に実行できる定義済みまたはユーザー定義のコマンドの名前付きセットです。  ターゲット コマンド ライン オプション \(**\/t**\) を使用して、ビルド ターゲットを指定します。  `myproject` サンプル プロジェクトの場合、定義済みの **clean** ターゲットがデバッグ フォルダーのすべてのファイルを削除し、新しいログ ファイルを作成します。  
  
 コマンド プロンプトで次のコマンドを入力して、`myproject` を削除します。  
  
 `msbuild myproject.vcxproj /t:clean`  
  
### MSBuild とビルド プロパティの併用  
 プロパティ コマンド ライン オプション \(**\/p**\) によって、プロジェクト ビルド ファイルのプロパティをオーバーライドできます。  `myproject` サンプル プロジェクトでは、`Configuration` プロパティによってリリース用またはデバッグ用のビルド構成が指定されます。  また、ビルド済みアプリケーションを実行するためのオペレーティング システムが、`Platform` プロパティで指定されます。  
  
 コマンド プロンプトで次のコマンドを入力して、32 ビット Windows で実行される予定の `myproject` アプリケーションのデバッグ ビルドを作成します。  
  
 `msbuild myproject.vcxproj /p:configuration=debug /p:platform=win32`  
  
 `myproject` サンプル プロジェクトが、64 ビット Windows の構成と、別の `myplatform` という名前のカスタム オペレーティング システムの構成も定義していると想定します。  
  
 コマンド プロンプトで次のコマンドを入力して、64 ビット Windows で実行するリリース ビルドを作成します。  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=x64`  
  
 コマンド プロンプトで次のコマンドを入力して、`myplatform` のリリース ビルドを作成します。  
  
 `msbuild myproject.vcxproj /p:configuration=release /p:platform=myplatform`  
  
### MSBuild と 64 ビットのコンパイラおよびツールの併用  
 64 ビット Windows に [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] がインストールされている場合、既定では、64 ビットの x64 ネイティブおよびクロス ツールがインストールされます。  `PreferredToolArchitecture` プロパティを設定することで、アプリケーションのビルドには 64 ビットのコンパイラおよびツールが使用されるように [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] を構成できます。  このプロパティは、プロジェクトの構成とプラットフォームのプロパティには影響しません。  既定では、32 ビット版のツールが使用されます。  64 ビット版のコンパイラおよびツールを指定するには、次のプロパティ グループ要素を Myproject.vcxproj プロジェクト ファイル内の \<Import \/\> 要素 `Microsoft.Cpp.default.props` の後に追加します。  
  
```xml  
<PropertyGroup>  
    <PreferredToolArchitecture>x64</PreferredToolArchitecture>  
</PropertyGroup>  
```  
  
 64 ビット ツールを使用してアプリケーションをビルドするには、コマンド プロンプトで次のコマンドを入力します。  
  
 `msbuild myproject.vcxproj /p:PreferredToolArchitecture=x64`  
  
### MsBuild と他のツールセットの併用  
 他バージョンの [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 用のツールセットおよびライブラリがインストールされている場合、[!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] では、現在の [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] バージョンまたはインストールされている別のバージョン用にアプリケーションをビルドできます。  たとえば [!INCLUDE[cpp_dev11_long](../build/includes/cpp_dev11_long_md.md)] がインストールされている場合、Windows XP 用の [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 11.0 ツールセットを指定するには、次のプロパティ グループ要素を Myproject.vcxproj プロジェクト ファイル内の Microsoft.Cpp.props `<Import />` 要素の後に追加します。  
  
```xml  
<PropertyGroup>  
    <PlatformToolset>v110_xp</PlatformToolset>  
</PropertyGroup>  
```  
  
 [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] 11.0 Windows XP ツールセットでプロジェクトをリビルドするには、次のコマンドのいずれかを入力します。  
  
 `msbuild myproject.vcxproj /p:PlatformToolset=v110_xp /t:rebuild`  
  
 `msbuild myproject.vcxproj /t:rebuild`  
  
### MSBuild のカスタマイズの追加  
 [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] では、さまざまな方法でビルド処理をカスタマイズできます。  次のトピックでは、[!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] プロジェクトにカスタム ビルド ステップ、ツール、およびイベントを追加する方法を示します。  
  
-   [方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する](../Topic/How%20to:%20Add%20a%20Custom%20Build%20Step%20to%20MSBuild%20Projects.md)  
  
-   [方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)  
  
-   [方法: MSBuild プロジェクトでビルド イベントを使用する](../build/how-to-use-build-events-in-msbuild-projects.md)