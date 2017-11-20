---
title: "-GENPROFILE、FASTGENPROFILE (プロファイル インストルメント ビルドの生成) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GENPROFILE
- FASTGENPROFILE
- /GENPROFILE
- /FASTGENPROFILE
helpviewer_keywords:
- GENPROFILE
- FASTGENPROFILE
ms.assetid: deff5ce7-46f5-448a-b9cd-a7a83a6864c6
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e3b0f986d4bc805a3cac1ec49193f3749f31af9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="genprofile-fastgenprofile-generate-profiling-instrumented-build"></a>/GENPROFILE、/FASTGENPROFILE (プロファイル インストルメント ビルドの生成)
ガイド付き最適化のプロファイル (PGO) をサポートするために、リンカーによる .pgd ファイルの生成を指定します。  /GENPROFILE と /FASTGENPROFILE は、それぞれに異なる既定のパラメーターを使用します。 プロファイル中に精度を速度とメモリ使用量よりも優先する場合は、/GENPROFILE を使用します。 精度よりも少ないメモリ使用量と速度を優先する場合は、/FASTGENPROFILE を使用します。  
  
## <a name="syntax"></a>構文  
  
```  
/{GENPROFILE|FASTGENPROFILE}[:{COUNTER32|COUNTER64|EXACT|MEMMAX=#|MEMMIN=#|NOEXACT|NOPATH|NOTRACKEH|PATH|PGD=filename|TRACKEH}]   
```  
  
## <a name="remarks"></a>コメント  
 COUNTER32 &#124;です。COUNTER64  
 32 ビットのプローブのカウンターを使用する場合は COUNTER32 を使用し、64 ビットのプローブのカウンターを使用する場合は COUNTER64 を使用します。 /GENPROFILE を指定する場合、既定値は COUNTER64 です。 /FASTGENPROFILE を指定する場合、既定値は COUNTER32 です。  
  
 正確な &#124;です。NOEXACT は、  
 プローブのスレッドセーフであるインターロックされたインクリメントを指定する場合は、EXACT を使用します。 NOEXACT は、プローブの保護されていないインクリメント操作を指定します。 既定では、NOEXACT です。  
  
 MEMMAX=value、MEMMIN=value  
 MEMMAX と MEMMIN を使用して、メモリ内のトレーニング データの最大と最小の予約サイズを指定します。 値は、予約するメモリ量 (バイト単位) です。  既定では、これらの値は内部ヒューリスティックによって決定されます。  
  
 パス &#124;です。場合は、NOPATH  
 一意の関数パスごとに別の PGO カウンターのセットを指定する場合は、PATH を使用します。 関数ごとにカウンターのセットを 1 つだけ指定する場合は、NOPATH を使用します。   /GENPROFILE を指定する場合、既定値は PATH です。 /FASTGENPROFILE を指定する場合、既定値は NOPATH です。  
  
 TRACKEH &#124;です。NOTRACKEH  
 トレーニング中に例外がスローされた場合に、追加のカウンターを使用して正確なカウントを保持するかどうかを指定します。 正確な数を保持するために追加のカウンターを指定する場合は、TRACKEH を使用します。 例外処理を使用していないコード、または、トレーニング シナリオで例外が発生しないコードの場合に 1 つのカウンターを指定する場合は、NOTRACKEH を使用します。  /GENPROFILE を指定する場合、既定値は TRACKEH です。 /FASTGENPROFILE を指定する場合、既定値は NOTRACKEH です。  
  
 PGD = ファイル名  
 .pgd ファイルの基本ファイル名を指定します。 既定では、リンカーは、基本の実行可能イメージのファイル名に .pgd 拡張子を付けて使用します。  
  
 /GENPROFILE と /FASTGENPROFILE のオプションは、ガイド付き最適化のプロファイル (PGO) のためのアプリケーション トレーニングをサポートするために必要なプロファイル インストルメンテーション ファイルを生成するようにリンカーに指示します。 アプリケーションのトレーニングによって生成されたプロファイル情報が、ビルド中に入力として使用され、対象のプログラム全体の最適化が実行されます。   アプリのトレーニング中とビルド中にパフォーマンスのためのさまざまなプロファイル機能を制御する追加のオプションを設定することができます。 /GENPROFILE で指定される既定のオプションを使用すると、特に大規模で複雑なマルチ スレッドのアプリの場合に、最も正確な結果が得られます。 /FASTGENPROFILE オプションでは、精度と引き換えに、トレーニング中のメモリの使用量を削減してパフォーマンスを向上させることができる、別の既定値が使用されます。  
  
 /GENPROFILE または /FASTGENPROFILE を使用してビルドした後に、インストルメントされたアプリを実行すると、プロファイル情報がキャプチャされます。 /USEPROFILE オプションを指定すると、この情報がリンカーによって使用されます。 アプリをトレーニングする方法の詳細について、および収集したデータの詳細については、「ガイド付き最適化のプロファイル」を参照してください。  
  
 /GENPROFILE または /FASTGENPROFILE を指定するときには、/LTCG も指定する必要があります。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)   
 [/LTCG (リンク時コード生成)](../../build/reference/ltcg-link-time-code-generation.md)