---
title: "pgosweep |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c703bc68a36dd21c837e62738d9d2c2631502a0d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="pgosweep"></a>pgosweep
.Pgc ファイルに、実行中のプログラムからすべてのプロファイル データを書き込めませんプロファイル ガイド付き最適化のために使用します。  
  
## <a name="syntax"></a>構文  
  
```  
pgosweep [options] image pgcfile  
```  
  
#### <a name="parameters"></a>パラメーター  
 `options`  
 オプションのパラメーターを空白にすることができます。 有効値、`options`次に示します。  
  
-   **/?** または**/help、**ヘルプ メッセージが表示されます。  
  
-   **/noreset、**ランタイム データ構造体に含まれる数を保持します。  
  
 `image`  
 コンパイラ オプション/LTCG:PGINSTRUMENT を使用して作成された .exe または .dll ファイルの完全パス。  
  
 `pgcfile`  
 .Pgc ファイルをこのコマンドは書き込みのデータをカウントします。  
  
## <a name="remarks"></a>コメント  
 このコマンドは、/LTCG:PGINSTRUMENT コンパイラ オプションを使用してビルドされたプログラムで機能します。 これにより、実行中のプログラムを中断し、新しい .pgc ファイルにプロファイル データを書き込みます。 既定では、コマンドは、個々 の書き込み操作の後にカウントをリセットします。 指定した場合、 **/noreset**オプション、コマンドは、値が記録されますが、プログラムの実行にリセットされません。 このオプションは、重複するデータ、プロファイル データを後で取得する場合。  
  
 用途`pgosweep`プロファイル情報は、アプリケーションのランタイムをだけを取得することです。 たとえば、実行する`pgosweep`すぐにアプリケーションを起動し、そのファイルを破棄します。 これは、スタートアップ コストに関連付けられているプロファイル データを削除します。 その後、実行`pgosweep`アプリケーションを終了する前にします。 収集されたデータになりましたランタイムからのみプロファイル情報。  
  
 .Pgc ファイル名を指定する場合 (`pgcfile`) は、標準の形式を使用する*appname! n*.pgc です。 この形式を使用する場合、コンパイラは/LTCG:PGO フェーズでこのデータを検索します。 使用する必要があります、標準の形式を使用しない場合[pgomgr](../../build/reference/pgomgr.md) .pgc ファイルをマージします。  
  
## <a name="example"></a>例  
  
```  
pgosweep myapp.exe myapp!1.pgc  
```  
  
 この例では`pgosweep`myapp!1.pgc に myapp.exe の現在のプロファイル情報を書き込みます。  
  
## <a name="see-also"></a>関連項目  
 [ガイド付き最適化の手動プロファイル用ツール](../../build/reference/tools-for-manual-profile-guided-optimization.md)