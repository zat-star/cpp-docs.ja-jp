---
title: "ユニバーサル Windows アプリ (C++) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 357121cc-d390-4bae-b34a-39614861a9f4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a293f833de7bc575209089362bcaf146d074684b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2018
---
# <a name="universal-windows-apps-c"></a>ユニバーサル Windows アプリ (C++)
ユニバーサル Windows プラットフォーム (UWP) アプリは、一連のさまざまなデバイス上のさまざまな画面サイズに合わせて調整されるコンテンツを中心とした、シンプルなユーザー インターフェイスを強調するデザインの原則を具体化します。 XAML マークアップで UI を作成し、ネイティブ C++ で分離コードを作成します。 さらに他の言語で記述された UWP アプリケーションで使用可能なコンポーネント (DLL) を作成できます。 UWP アプリの API サーフェスは、Windows ランタイムでは、さまざまなオペレーティング システムのサービスを提供するための十分に考慮されたライブラリです。  

> [!TIP]  
> Windows 10 用 Microsoft ストアを介して展開用の既存のデスクトップ アプリケーションをパッケージ化するのに、デスクトップ アプリを実行するコンバーターを使用できます。 詳しくは、「[Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project)」(Centennial プロジェクトでの Visual C++ ランタイムの使用) および「[Bring your desktop app to the Universal Windows Platform (UWP) with the Desktop Bridge](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root)」(Desktop Bridge でデスクトップ アプリをユニバーサル Windows プラットフォーム (UWP) 対応にする) をご覧ください。
  
  
## <a name="uwp-apps-that-use-ccx"></a>C++/CX を使用する UWP アプリ  
  
|||  
|-|-|  
|[Visual C++ の言語リファレンス (C++/CX)](../cppcx/visual-c-language-reference-c-cx.md)|Windows ランタイム Api の C++ の消費量を簡略化し、例外に基づいているエラー処理を有効にする拡張機能のセットについて説明します。|  
|[アプリケーションとライブラリのビルド (C++/CX)](../cppcx/building-apps-and-libraries-c-cx.md)|C ++/CX アプリケーションまたはコンポーネントからアクセスできるスタティック ライブラリと DLL を作成する方法について説明します。|  
|[チュートリアル: C++ を使った初めての UWP アプリを作成します。](https://docs.microsoft.com/en-us/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)|C++ の UWP アプリ開発の基本的な概念を説明するチュートリアルです。 (Windows 10 での UWP 開発に関してはまだ更新されていません。)|  
|[C++ での Windows ランタイム コンポーネントを作成します。](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)|他の UWP アプリやコンポーネントを使用できる Dll を作成する方法について説明します。|  
|[ゲームの開発](https://docs.microsoft.com/en-us/windows/uwp/gaming/)|DirectX および C++ を使ってゲームを作成する方法について説明します。|  
  
## <a name="uwp-apps-that-use-the-windows-runtime-c-template-library-wrl"></a>Windows ランタイム C++ テンプレート ライブラリ (WRL) を使用する UWP アプリ 
 Windows ランタイム C++ テンプレート ライブラリは、例外を必要としない環境での Windows ランタイムを ISO C のコードからアクセスできる低レベルの COM インターフェイスを提供します。 ほとんどの場合、使用をお勧めする C + + CX UWP アプリ開発用 Windows ランタイム C++ テンプレート ライブラリの代わりにします。 Windows ランタイム C++ テンプレート ライブラリの概要については、次を参照してください。 [Windows ランタイム C++ テンプレート ライブラリ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)です。  
  
## <a name="see-also"></a>参照  
 [Visual C++](../visual-cpp-in-visual-studio.md)

