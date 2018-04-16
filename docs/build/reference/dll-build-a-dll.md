---
title: "DLL (DLL のビルド) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /dll
dev_langs:
- C++
helpviewer_keywords:
- -DLL linker option
- /DLL linker option [C++]
- exporting DLLs [C++], specifying exports
- DLLs [C++], building
- DLL linker option [C++]
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28a501590e127e5f27a465366611b4dbf3be175c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="dll-build-a-dll"></a>/DLL (DLL のビルド)
```  
/DLL  
```  
  
## <a name="remarks"></a>コメント  
 /DLL オプションは、メイン出力ファイルと DLL をビルドします。 通常、DLL には、別のプログラムで使用できるエクスポートが含まれます。 使用の推奨される順序で一覧表示、エクスポートを指定するための 3 つの方法はあります。  
  
1.  [方式](../../cpp/dllexport-dllimport.md)のソース コードで  
  
2.  [エクスポート](../../build/reference/exports.md).def ファイル内のステートメント  
  
3.  [/Export](../../build/reference/export-exports-a-function.md) LINK コマンド内の指定  
  
 プログラムでは、1 つ以上のメソッドを使用できます。  
  
 DLL をビルドする別の方法は、**ライブラリ**モジュール定義ステートメントです。 /BASE し、/DLL オプションは一緒に相当する、**ライブラリ**ステートメントです。  
  
 開発環境以外では、このオプションを指定しません。このオプションは、コマンドラインでのみ使用されます。 アプリケーション ウィザードを使用して、DLL プロジェクトを作成するときに、このオプションが設定されます。  
  
 .Dll を作成する前に、準備手順で、インポート ライブラリを作成する場合を渡す必要がある同じ一連のオブジェクト ファイル、.dll を構築するときにインポート ライブラリを構築するときに渡したものとに注意してください。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  クリックして、**構成プロパティ**フォルダーです。  
  
3.  クリックして、**全般**プロパティ ページ。  
  
4.  変更、**構成の種類**プロパティです。  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>」を参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)