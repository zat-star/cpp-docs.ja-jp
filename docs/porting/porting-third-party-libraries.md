---
title: "サードパーティ ライブラリの移植 | Microsoft ドキュメント"
ms.custom: 
ms.date: 01/10/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- 3rd-party libraries
- vspkg
ms.assetid: b055ed20-8a9e-45b2-ac2a-e3d94271c009
caps.latest.revision: 0
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 8630a5c0b97b85e0dc75e8b470974bb7d223a511
ms.openlocfilehash: 1d85010b6068d52d8522875a3c47561ad777d345
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---

# <a name="porting-third-party-libraries"></a>サード パーティ ライブラリの移植

プロジェクトを Visual C++ の現在のバージョンにアップグレードする場合は、プロジェクトで使用されているライブラリもアップグレードする必要があります。これにより、ライブラリとプロジェクトは、同じバージョンおよび種類のコンパイラでビルドされます。 詳細については、「[アップグレード時の潜在的な問題の概要](overview-of-potential-upgrade-issues-visual-cpp.md)」 を参照してください。 

## <a name="introducing-vcpkg"></a>vcpkg の概要
これまでは、サードパーティ ライブラリの検索とアップグレードが困難な作業となる場合がありました。 サードパーティ製の C++ オープンソース ライブラリの取得とリビルドを簡単にするために、Visual C++ チームは、**VC++ パッケージ ツール**または **vcpkg** と呼ばれるコマンドライン ツールを作成しました。 vcpkg には、多くの一般的な C++ オープンソース ライブラリの、検索可能なカタログがあります。 vcpkg コマンドラインから、カタログ内の任意のライブラリを直接インストールすることができます。 ライブラリをインストールすると、vcpkg によってコンピューターにディレクトリ ツリーが作成され、このフォルダー内に .h、.lib、およびバイナリが追加されます。 このフォルダーは、コンパイル コマンドラインで使用することも、vcpkg integrate install コマンドによって Visual Studio 2015 以降に統合することもできます。 ライブラリの場所を統合すると、Visual Studio でそのライブラリの場所を検索したり、作成した新しいプロジェクトに追加したりすることができます。 ライブラリを使用するには、それを #include するだけです。あとは、Visual Studio が自動的にプロジェクト設定への .lib パスを追加し、ソリューション フォルダーに dll をコピーします。

## <a name="acquisition-and-usage"></a>取得と使用

vcpkg は [vcpkg GitHub repo][vcpkg](https://github.com/Microsoft/vcpkg/)からダウンロードできます。

 - カタログ内のライブラリを検索するには: vcpkg search <LibName>
 - ライブラリ (たとえば Boost) を取得するには: vcpkg install boost
 - 現在インストールされている lib を一覧表示するには: vcpkg list

ブログの投稿 [Vcpkg: a tool to acquire and build C++ open source libraries on Windows](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) (vcpkg: Windows 上で C++ オープンソース ライブラリを取得およびビルドするツール) に、vcpkg のしくみに関する説明と、サポートされているライブラリの一覧が記載されています。 毎週、この一覧は更新されます。

## <a name="reporting-issues"></a>レポートの問題
vcpkg カタログ内に目的のライブラリが存在しない場合は、[GitHub リポジトリ](https://github.com/Microsoft/vcpkg/issues)に掲載されている問題点を参照できます。コミュニティおよび Visual C++ チームは、内容を確認することで、該当するライブラリのポート ファイルを作成できる可能性があります。

サードパーティ独自のライブラリ (非オープン ソース) の場合、ライブラリの製造元に問い合わせることをお勧めします。 ただし、使用する独自仕様の lib のうちアクセスできないものがあれば、どちらの lib であるかをお知らせください (連絡先は vcupgrade@microsoft.com です)。

  
## <a name="see-also"></a>関連項目  
 [Visual C++ 移植とアップグレードのガイド](visual-cpp-porting-and-upgrading-guide.md)

