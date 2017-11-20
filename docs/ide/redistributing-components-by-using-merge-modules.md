---
title: "マージ モジュールを使用して、コンポーネントの再配布 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- merge modules, using
- redistributing applications, using merge modules
ms.assetid: 93b84211-bf9b-4a78-9f22-474ac2ef7840
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 14eb80452a9b5ceefeea7ff204c42288b7542c5a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="redistributing-components-by-using-merge-modules"></a>マージ モジュールを使用したコンポーネントの再配布
Visual Studio を含む[マージ モジュール](http://msdn.microsoft.com/library/aa367434)アプリケーションと共に再配布するためのライセンスが Visual C コンポーネントごとにします。 マージ モジュールが Windows インストーラーのセットアップ ファイルにコンパイルされるときに、特定のプラットフォームのコンピューターへの特定の DLL の配置が有効になります。 セットアップ ファイルでは、そのマージ モジュールがアプリケーションの必須コンポーネントであることを指定します。 マージ モジュールは \program \merge モジュールにインストールされている Visual Studio がインストールされているときに\\です。 (Visual C Dll の非デバッグ バージョンのみ再頒布できます。)再頒布ライセンスされているマージ モジュールの一覧へのリンクおよび詳細については、次を参照してください。 [Visual c ファイルの再配布](../ide/redistributing-visual-cpp-files.md)です。  
  
 マージ モジュールを使用すると、再頒布可能パッケージの Visual C Dll を %SYSTEMROOT%\system32\ フォルダーにインストールできるようにします。 (Visual Studio 自体は、この手法を使用します)。ただし、このフォルダーへのインストールは、インストールしているユーザーに管理者権限がないと失敗します。  
  
 アプリケーションにサービスを提供する必要がある場合、また、複数のバージョンの DLL に依存している場合は、マージ モジュールを使用することはお勧めしません。 1 つの DLL にさまざまなバージョンの DLL がある場合、その複数バージョンの DLL に対する複数のマージ モジュールを 1 つのインストーラーに含めることはできません。また、マージ モジュールによって、アプリケーションとは別に DLL にサービスを提供することが難しくなります。 代わりに、Visual C 再頒布可能パッケージをインストールすることをお勧めします。  
  
## <a name="see-also"></a>関連項目  
 [Visual C++ ファイルの再配布](../ide/redistributing-visual-cpp-files.md)