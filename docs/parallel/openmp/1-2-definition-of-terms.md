---
title: "1.2 用語の定義 |Microsoft ドキュメント"
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
ms.assetid: fcaa8eb8-bbbf-4a24-ad0e-e299c442db79
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab188c32c633092efc562d0432ebb7c5662b5ff8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="12-definition-of-terms"></a>1.2 用語の定義
次の用語は、このドキュメントで使用されます。  
  
 barrier  
 同期ポイント チーム内のすべてのスレッドが到達する必要があります。  各スレッドは、チームのすべてのスレッドがこの時点で到着するまで待機します。 ディレクティブと実装によって作成された暗黙のバリアによって識別される明示的な障壁があります。  
  
 construct  
 コンストラクトは、ステートメントを示します。 ディレクティブと後続の構造化ブロックで構成されます。 一部のディレクティブは、構造の一部ではないことに注意してください。 (を参照してください*openmp ディレクティブ*で[付録 C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md))。  
  
 ディレクティブ  
 C または C++ **#pragma**続けて、 **omp**識別子、その他のテキスト、および改行します。 ディレクティブは、プログラムの動作を指定します。  
  
 動的範囲  
 すべてのステートメント、*構文範囲*、構文上の範囲内のステートメントの実行の結果として実行される関数内のすべてのステートメントとします。 呼びますが動的範囲、*地域*です。  
  
 構文範囲  
 ステートメントに構文的に含まれる、*構造化ブロック*です。  
  
 マスター スレッド  
 チームを作成したスレッドと、*並列領域*を入力します。  
  
 並列領域  
 OpenMP の parallel コンストラクトにバインドし、複数のスレッドによって実行される可能性があるステートメント。  
  
 private  
 プライベート変数の参照を行っているスレッドに一意の記憶域のブロックを名前します。 変数をプライベートに指定するいくつかの方法があることに注意してください: 並行領域内の定義を**threadprivate**ディレクティブ、**プライベート**、 **firstprivate**、**lastprivate**、または**削減**句、または変数としての使用、**の**のループ制御変数、**の**ループ直後、**の**または**の並列**ディレクティブです。  
  
 region  
 動的範囲。  
  
 シリアル領域  
 ステートメントによってのみ実行される、*マスター スレッド*動的範囲のいずれかの外部で*並列領域*です。  
  
 シリアル化します。  
 チームが、シングル スレッドのみ (つまり、parallel コンストラクトのマスター スレッド)、シリアル、構造化ブロック内のステートメントの実行順序とで構成されるスレッドの parallel コンストラクトを実行する (ブロックされていない場合と同じ順序パーツparallel コンストラクトの)、およびによって返される値に影響しない**omp_in_parallel()** (いずれかの影響とは別には、parallel コンストラクトを入れ子になった)。  
  
 shared  
 共有変数は、単一ブロック記憶域の名前します。 この変数にアクセスする、チーム内のすべてのスレッドは、この 1 つのブロック記憶域にアクセスします。  
  
 構造化ブロック  
 構造化ブロックは、1 つのエントリと 1 つの終了を持つステートメント (単一または複合) です。 ステートメントには、構造化ブロックはありませんが、そのステートメントの内外にジャンプ場合 (の呼び出しを含む**longjmp**(3 C) の使用、または**スロー**への呼び出し**終了**は許可されて)。 開くときに常に実行が開始された場合、複合ステートメントは、構造化ブロック**{**と常に終わりの終了**}**です。 式ステートメント、選択ステートメント、反復ステートメント、または**再試行**ブロックは、構造化ブロックで囲まれた対応する複合ステートメントが取得された場合**{**と**}**構造化ブロックになります。 ジャンプ ステートメント、ラベル付きステートメント、または宣言ステートメントは、構造化ブロックではないです。  
  
 チーム  
 1 つ以上のスレッド構成の実行時に協力します。  
  
 スレッド  
 シリアル、制御フロー、一連のプライベート変数は、共有変数へのアクセスを持つ実行エンティティです。  
  
 変数  
 オブジェクトの名前を示す識別子、名前空間の名前で修飾できます。