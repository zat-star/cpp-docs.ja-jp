---
title: "方法: 複数の PGO プロファイルを 1 つのプロファイルにマージ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- merging profiles
- profile-guided optimizations, merging profiles
ms.assetid: aab686b5-59dd-40d1-a04b-5064690f65a6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 880e9fbba7852a9a7919e73f80b73e34394cd037
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-merge-multiple-pgo-profiles-into-a-single-profile"></a>方法 : 複数の PGO プロファイルを単一のプロファイルにマージする
最適化のガイド付きプロファイル (PGO) は、プロファイリングが実行されているシナリオに基づく最適化されたバイナリを作成するための優れたツールです。 いくつかの重要なまだ個別シナリオがある場合は、アプリケーションが複数の異なるシナリオから PGO を使用する 1 つのプロファイルを作成します。 Visual Studio で、PGO マネージャー、Pgomgr.exe は、このジョブです。  
  
 プロファイルに結合の構文です。  
  
```  
pgomgr /merge[:num] [.pgc_files] .pgd_files  
```  
  
 ここで`num`このマージに使用されているオプションの重量がします。 重みは、他のユーザーよりも重要である一部のシナリオがある場合、または複数回実行するのには、シナリオがある場合によく使用されます。  
  
> [!NOTE]
>  PGO マネージャーは、古いプロファイル データには機能しません。 .Pgd ファイル .pgc ファイルをマージするには、.pgc ファイルを .pgd ファイルを生成したのと同じリンク呼び出しで作成された実行可能ファイルで生成される必要があります。  
  
## <a name="example"></a>例  
 この例では、PGO マネージャーに追加されます pgcFile.pgc pgdFile.pgd 6 回。  
  
```  
pgomgr /merge:6 pgcFile.pgc pgdFile.pgd  
```  
  
## <a name="example"></a>例  
 この例では、PGO マネージャーは追加 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd、各 .pgc ファイルの 2 倍にします。  
  
```  
pgomgr /merge:2 pgcFile1.pgc pgcFile2.pgc pgdFile.pgd  
```  
  
## <a name="example"></a>例  
 .Pgc ファイルを使用せず、PGO マネージャーが実行される場合は、任意の文字が続き、感嘆符 (!) が付いた .pgd ファイルとして同じ名前を持つすべての .pgc ファイル用のローカル ディレクトリが検索されます。 ローカルのディレクトリはファイル test.pgd、test!1.pgc、test2.pgc、および test!hello.pgc、し、ローカル ディレクトリから次のコマンドが実行される場合、test!1.pgc と test!hello.pgc をマージする test.pgd です。  
  
```  
pgomgr /merge test.pgd  
```  
  
## <a name="see-also"></a>参照  
 [ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)