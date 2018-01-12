---
title: "方法: MSBuild プロジェクトにカスタム ビルド ステップを追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: msbuild.cpp.howto.addcustombuildstep
dev_langs: C++
helpviewer_keywords: 'msbuild (c++), howto: add a custom build step'
ms.assetid: a20a0c47-4df4-4754-a1f0-a94a99958916
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d664b9fad6a9ec67dc009a90171119036dc13cde
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-add-a-custom-build-step-to-msbuild-projects"></a>方法: MSBuild プロジェクトにカスタム ビルド ステップを追加する
カスタム ビルド ステップは、ユーザー定義のビルドにおける手順です。 カスタム ビルド ステップは、他のように動作*コマンド ツール*など、標準のコンパイルまたはリンクのツールの手順のステップします。  
  
 プロジェクト ファイル (.vcxproj) でカスタム ビルド ステップを指定します。 手順では、追加の入力または出力ファイル、および表示するメッセージを実行するコマンドラインを指定できます。 場合**MSBuild**出力ファイルが、入力ファイルに対して最新ではないこと、コマンドを実行し、メッセージが表示されますかを指定します。  
  
 カスタムのビルドの場所にビルドのターゲットのシーケンスのステップを指定するの一方または両方を使用して、`CustomBuildAfterTargets`と`CustomBuildBeforeTargets`プロジェクト ファイル内の XML 要素です。 たとえば、リンク ツールのターゲット後、マニフェスト ツールのターゲットの前に、カスタム ビルド ステップを実行するかを指定できます。 実際の使用可能なターゲットのセットは、特定のビルドに依存します。  
  
 指定して、`CustomBuildBeforeTargets`要素は、特定のターゲットが実行される前に、カスタム ビルド ステップを実行する、`CustomBuildAfterTargets`要素は、特定のターゲットが実行されると後の手順を実行するか、両方の要素を 2 つの隣接するターゲットの間での手順を実行します。 後に、既定の場所で、カスタム ビルド ツールを実行するいずれの要素が指定されている場合、**リンク**ターゲットです。  
  
 カスタム ビルド ステップとカスタム ビルド ツールで指定された情報を共有、`CustomBuildBeforeTargets`と`CustomBuildAfterTargets`XML 要素です。 そのため、これらのターゲットを指定 1 回だけでは、プロジェクト ファイルです。  
  
### <a name="to-define-what-is-executed-by-the-custom-build-step"></a>カスタム ビルド ステップによって実行される対象を定義するには  
  
1.  プロジェクト ファイルにプロパティのグループを追加します。 このプロパティ グループには、次の例で示すように、コマンド、その入力と出力、および、メッセージを指定します。 この例で作成した main.cpp ファイルからの .cab ファイルの作成[チュートリアル: Visual C プロジェクトを作成するを使用して MSBuild](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)です。  
  
    ```  
    <ItemDefinitionGroup>  
      <CustomBuildStep>  
        <Command>makecab.exe $(ProjectDir)main.cpp $(TargetName).cab</Command>  
        <Outputs>$(TargetName).cab</Outputs>  
        <Inputs>$(TargetFileName)</Inputs>  
      </CustomBuildStep>  
    </ItemDefinitionGroup>  
    ```  
  
### <a name="to-define-where-in-the-build-the-custom-build-step-will-execute"></a>ここで、ビルドで、カスタム ビルド ステップを実行するかを定義するには  
  
1.  プロジェクト ファイルに次のプロパティ グループを追加します。 両方のターゲットを指定するか省略することができますと 1 つだけの場合、特定のターゲットの前後を実行するカスタム ステップします。 この例のように指示**MSBuild**コンパイル手順の後に、リンクの手順の前に、カスタムの手順を実行します。  
  
    ```  
    <PropertyGroup>  
      <CustomBuildAfterTargets>ClCompile</CustomBuildAfterTargets>  
      <CustomBuildBeforeTargets>Link</CustomBuildBeforeTargets>  
    </PropertyGroup>  
    ```  
  
## <a name="see-also"></a>参照  
 [チュートリアル: MSBuild を使用した Visual C プロジェクトの作成](../build/walkthrough-using-msbuild-to-create-a-visual-cpp-project.md)   
 [方法: MSBuild プロジェクトでビルド イベントを使用](../build/how-to-use-build-events-in-msbuild-projects.md)   
 [方法: MSBuild プロジェクトにカスタム ビルド ツールを追加する](../build/how-to-add-custom-build-tools-to-msbuild-projects.md)