---
title: "方法: Windows デスクトップ アプリケーションでの Windows 10 SDK の使用 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: eed6421e-9355-44a6-9582-3f1d453a6d44
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: Windows デスクトップ アプリケーションでの Windows 10 SDK の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vs_dev14](../mfc/includes/vs_dev14_md.md)] でクラシック Windows デスクトップ プロジェクトを作成するときには、Windows 8.1 の SDK でビルドするように既定で設定されています。 このバージョンの Windows SDK は Windows 10 を含む最近のすべての Windows リリースと互換性がありますが、Windows 10 SDK に含まれる最新の Windows API および CRT 関数を含んでいません。 新しい API を使用する場合は、Windows 10 SDK を参照するようにプロジェクトのターゲットを変更できます。  
  
 [!INCLUDE[vs_dev14](../mfc/includes/vs_dev14_md.md)] および Windows 10 SDK 以降、CRT ライブラリは、ユニバーサル Windows アプリで使用可能な関数を含んだもの \(ucrtbase\) と、その他のすべてを含んでいるもの \(vcruntime140\) の 2 つに分割されました。 Windows 10 SDK には、多数の C99 関数をはじめとする新しい関数が含まれているため、これらの関数を使用するために、次の手順に従う必要があります。 「[CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)」を参照してください。  
  
### Windows 10 SDK をターゲットとするには  
  
1.  Windows 10 SDK がインストールされていることを確認します。 Windows 10 SDK は、[Windows 10 開発者ツール](http://go.microsoft.com/fwlink/?LinkID=617631)の一部としてインストールされます。  
  
2.  プロジェクト ノードのショートカット メニューを開き、**\[Retarget SDK Version\] \(SDK バージョンの再ターゲット\)** をクリックします。  
  
     ![SDK バージョンの再ターゲット](../windows/media/retargetingwindowssdk1.png "RetargetingWindowsSDK1")  
  
     **\[ソリューション操作の再ターゲット\]** ダイアログが表示されます。  
  
     ![ソリューション操作の再ターゲット](../windows/media/retargetingwindowssdk2.png "RetargetingWindowsSDK2")  
  
3.  **\[ターゲット プラットフォーム バージョン\]** ドロップダウン リストで、ターゲットとする Windows 10 SDK を選択するか、変更を加えない場合には 8.1 を選択します。 \[OK\] ボタンを選択して変更を適用します。  
  
     このコンテキストでは、8.1 が、Windows 8、Windows Server 2012、Windows 7、Windows Server 2008、および Windows Vista との下位互換性も備えた Windows SDK バージョンを参照することに注意してください。  
  
     この手順が成功すると、出力ウィンドウに次のテキストが表示されます。  
  
     `再ターゲットの終了: 完了 1、失敗 0、スキップ 0`  
  
4.  プロジェクト プロパティを開いて**\[構成プロパティ\]、\[全般\]** セクションで、**\[Windows Target Platform Version\] \(Windows ターゲット プラットフォームのバージョン\)** の値を確認します。 ここで値を変更することは、この手順を実行するのと同じ効果があります。 「[\[全般\] プロパティ ページ \(プロジェクト\)](../Topic/General%20Property%20Page%20\(Project\).md)」を参照してください。  
  
     ![ターゲット プラットフォーム バージョン](../windows/media/retargetingwindowssdk3.png "RetargetingWindowsSDK3")  
  
     この操作は、ヘッダー ファイルとライブラリ ファイルへのパスを含むプロジェクトのマクロの値を変更します。 変更内容を確認するには、\[プロジェクト プロパティ\] ダイアログの \[Visual C\+\+ ディレクトリ\] セクションで、\[インクルード ディレクトリ\] などプロパティの 1 つを選択し、ドロップダウン リストのオープンを選択して、\< 編集 \> を選択します。**\[インクルード ディレクトリ\]** ダイアログが表示されます。  
  
     ![&#91;インクルード ディレクトリ&#93; ダイアログ ボックス](../windows/media/retargetingwindowssdk4.png "RetargetingWindowsSDK4")  
  
     **\[マクロ \>\>\]** ボタンを選択し、マクロの一覧を Windows SDK マクロまでスクロール ダウンして、すべての新しい値を確認します。  
  
     ![Windows SDK マクロ](../windows/media/retargetingwindowssdk5.png "RetargetingWindowsSDK5")  
  
5.  この操作を必要に応じて他のプロジェクトでも繰り返し、ソリューションをリビルドします。  
  
### Windows 8.1 SDK をターゲットとするには  
  
1.  プロジェクト ノードのショートカット メニューを開き、**\[Retarget SDK Version\] \(SDK バージョンの再ターゲット\)** をクリックします。  
  
2.  \[ターゲット プラットフォーム バージョン\] ドロップダウン リストで、8.1 を選択します。  
  
## 参照  
 [Windows Desktop Applications \(Visual C\+\+\)](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)