---
title: "LINK コマンド ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- link
dev_langs:
- C++
helpviewer_keywords:
- syntax, LINK command files
- command files [C++]
- LINK tool [C++]
- text files, passing arguments to LINK
- LINK tool [C++], command-line syntax
- command files [C++], LINK
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e585fb8fa11d4e3ffe8eff842baacb05f109754c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="link-command-files"></a>LINK コマンド ファイル
コマンド ファイルの形式でリンクには、コマンドライン引数を渡すことができます。 リンカーにコマンド ファイルを指定するには、次の構文を使用します。  
  
```  
LINK @commandfile  
```  
  
 `commandfile`テキスト ファイルの名前を指定します。 スペースやタブは使用できませんの間、アット マーク (@) とファイル名。 既定の拡張機能はありません。任意の拡張子を含めた、完全なファイル名を指定する必要があります。 ワイルドカードは使用できません。 ファイル名では、絶対または相対パスを指定できます。 リンクは、ファイルを検索する環境変数を使用しません。  
  
 コマンド ファイルで引数できますで区切るスペースまたはタブ (コマンド ライン) のように、改行文字。  
  
 コマンド ファイルでは、コマンドラインの一部またはすべてを指定できます。 LINK コマンドで 1 つ以上のコマンド ファイルを使用することができます。 リンクは、コマンドラインでその場所に、指定した場合と、コマンド ファイルの入力を受け入れます。 コマンド ファイルを入れ子にすることはできません。 しない限り、コマンド ファイルの内容がエコー、 [/NOLOGO](../../build/reference/nologo-suppress-startup-banner-linker.md)オプションを指定します。  
  
## <a name="example"></a>例  
 DLL をビルドする次のコマンドは独立したコマンド ファイル内のオブジェクト ファイルとライブラリの名前と、3 つ目コマンド/EXPORTS オプションの指定のファイルが使用。  
  
```  
link /dll @objlist.txt @liblist.txt @exports.txt  
```  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)