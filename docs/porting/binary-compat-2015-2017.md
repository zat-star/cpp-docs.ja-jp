---
title: "Visual Studio 2015 と Visual Studio 2017 の間の C++ バイナリ互換性 | Microsoft Docs"
ms.custom: 
ms.date: 09/21/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: binary compatibility, Visual C++
ms.assetid: 591580f6-3181-4bbe-8ac3-f4fbaca949e6
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d527a4e0647fe0e8471e168841a93512f4d1a9e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="c-binary-compatibility-between-visual-studio-2015-and-visual-studio-2017"></a>Visual Studio 2015 と Visual Studio 2017 の間の C++ バイナリ互換性


以前のバージョンの Visual Studio では、バージョンの異なるコンパイラ ツールセットやランタイム ライブラリで構築されたオブジェクト ファイル (OBJ)、スタティック ライブラリ (LIB)、ダイナミック ライブラリ (DLL)、実行可能ファイル (EXE) の間のバイナリ互換性が保証されていませんでした。 これが Visual Studio 2017 で変わりました。 Visual Studio 2015 と Visual Studio 2017 では、C++ ツールセットのメジャー番号が 14 になります (Visual Studio 2015 は v140、Visual Studio 2017 は v141)。 これは、ランタイム ライブラリといずれかのバージョンのコンパイラでコンパイルされたアプリケーションの両方に、ほとんどの部分において、バイナリ互換性があるという事実を反映するものです。 つまり、たとえば、Visual Studio 2017 で DLL を作成したら、Visual Studio 2015 でコンパイルしたアプリケーションからそれを利用できます。あるいは、2015 ツールセットでビルドしたアプリケーションで Visual Studio 2017 の再頒布可能ライブラリを利用できます。  

このルールには例外が 2 つあります。 以下の場合、バイナリ互換性は保証されません。  

1) スタティック ライブラリまたはオブジェクト ファイルが /GL コンパイラ スイッチでコンパイルされる場合。  

2) アプリケーションのコンパイルに使用されたツールセットよりバージョン番号が古い再頒布可能ライブラリをアプリケーションが使用する場合。 言い換えれば、プラットフォーム ツールセット v141 でプログラムをコンパイルした場合、アプリケーションで使用するあらゆる再頒布可能ライブラリを v141 以上でコンパイルする必要があります。  

## <a name="see-also"></a>参照  

[Visual C++ の変更履歴](..\porting\visual-cpp-change-history-2003-2015.md)


