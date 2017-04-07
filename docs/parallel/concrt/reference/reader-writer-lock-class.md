---
title: "reader_writer_lock クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- reader_writer_lock
- CONCRT/concurrency::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock_read
- CONCRT/concurrency::reader_writer_lock::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::lock
- CONCRT/concurrency::reader_writer_lock::lock_read
- CONCRT/concurrency::reader_writer_lock::try_lock
- CONCRT/concurrency::reader_writer_lock::try_lock_read
- CONCRT/concurrency::reader_writer_lock::unlock
dev_langs:
- C++
helpviewer_keywords:
- reader_writer_lock class
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
caps.latest.revision: 21
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
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: b5107923baa7d22e6a98c6617a22a883c4d84125
ms.lasthandoff: 03/17/2017

---
# <a name="readerwriterlock-class"></a>reader_writer_lock クラス
ローカルのみのスピンを行う、ライター優先キュー ベースのリーダー ライター ロックです。 ロックはライターに先入れ先出し (FIFO: First In First Out) アクセスを許可し、ライターに連続的な負荷がかかる状況ではリーダーが処理を実行できなくします。  
  
## <a name="syntax"></a>構文  
  
```
class reader_writer_lock;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-classes"></a>パブリック クラス  
  
|名前|説明|  
|----------|-----------------|  
|[reader_writer_lock::scoped_lock クラス](#scoped_lock_class)|取得するために使用できる例外安全な RAII ラッパー`reader_writer_lock`ライターとしてオブジェクトをロックします。|  
|[reader_writer_lock::scoped_lock_read クラス](#scoped_lock_read_class)|取得するために使用できる例外安全な RAII ラッパー`reader_writer_lock`リーダーとしてオブジェクトをロックします。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[reader_writer_lock](#ctor)|新しい `reader_writer_lock` オブジェクトを構築します。|  
|[~ reader_writer_lock デストラクター](#dtor)|`reader_writer_lock` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[lock](#lock)|ライターとしてのリーダー ライター ロックを取得します。|  
|[lock_read](#lock_read)|閲覧者のリーダー ライター ロックを取得します。 ライターがある場合は、アクティブなリーダーは、終了するまで待機しなければいけなくします。 リーダーは単に、ロックに関心を登録し、ライターによって解放されるまで待機します。|  
|[try_lock](#try_lock)|ブロックすることがなく、ライターとしてのリーダー ライター ロックを取得しようとしています。|  
|[try_lock_read](#try_lock_read)|ブロックせずに閲覧者としてのリーダー ライター ロックを取得しようとします。|  
|[unlock](#unlock)|リーダーまたはライターがロックされているユーザーに基づいてのリーダー ライター ロックを解除します。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[同期データ構造](../../../parallel/concrt/synchronization-data-structures.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `reader_writer_lock`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="lock"></a>ロック 

 ライターとしてのリーダー ライター ロックを取得します。  
  
```
void lock();
```  
  
### <a name="remarks"></a>コメント  
 利用する方が安全では多くの場合、 [scoped_lock](#scoped_lock_class)取得および解放するコンス トラクター、`reader_writer_lock`オブジェクトを例外のライターとして安全な方法です。  
  
 ライターがロックを取得しようとすると、後に後続のリーダーはライターが正常に取得およびロックを解放するまでブロックされます。 このロックはライターには偏りがあり、ライターの継続的な負荷の下での閲覧者が餓死することです。  
  
 ライターは、ライター ロックを終了する行で、次の書き込みを解放するように連結されます。  
  
 ロックが呼び出し元のコンテキストによって既に保持されている場合、 [improper_lock](improper-lock-class.md)例外がスローされます。  
  
##  <a name="lock_read"></a>lock_read 

 閲覧者のリーダー ライター ロックを取得します。 ライターがある場合は、アクティブなリーダーは、終了するまで待機しなければいけなくします。 リーダーは単に、ロックに関心を登録し、ライターによって解放されるまで待機します。  
  
```
void lock_read();
```  
  
### <a name="remarks"></a>コメント  
 使用する方が安全では多くの場合、 [scoped_lock_read](#scoped_lock_read_class)取得および解放するコンス トラクター、`reader_writer_lock`オブジェクト、例外内のリーダーとして安全な方法です。  
  
 ライター ロックを待機している場合は、リーダーはすべてのライターを取得およびロックを解放するまで待機します。 このロックはライターには偏りがあり、ライターの継続的な負荷の下での閲覧者が餓死することです。  
  
##  <a name="ctor"></a>reader_writer_lock 

 新しい `reader_writer_lock` オブジェクトを構築します。  
  
```
reader_writer_lock();
```  
  
##  <a name="dtor"></a>~ reader_writer_lock 

 `reader_writer_lock` オブジェクトを破棄します。  
  
```
~reader_writer_lock();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターが実行されるときに、ロックが保持されなく必要です。 未定義の動作に結果を保持もロックを消滅させるためにリーダー ライター ロックを許可します。  
  
##  <a name="scoped_lock_class"></a>reader_writer_lock::scoped_lock クラス  
 取得するために使用できる例外安全な RAII ラッパー`reader_writer_lock`ライターとしてオブジェクトをロックします。  
  
```
class scoped_lock;
``` 
## <a name="scoped_lock_ctor"></a>scoped_lock::scoped_lock 

構築、`scoped_lock`オブジェクトを取得し、`reader_writer_lock`で渡されるオブジェクト、`_Reader_writer_lock`ライターとしてパラメーター。 ロックが別のスレッドによって保持されている場合、この呼び出しはブロックされます。  
  
  
```
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Reader_writer_lock`  
 `reader_writer_lock`ライターとしてを取得するオブジェクト。  
  
## <a name="scoped_lock_dtor"></a>scoped_lock:: ~ scoped_lock 

破棄、`reader_writer_lock`オブジェクトし、そのコンス トラクターでロックを解放します。   

```
~scoped_lock();
```  
  
##  <a name="scoped_lock_read_class"></a>reader_writer_lock::scoped_lock_read クラス  
 取得するために使用できる例外安全な RAII ラッパー`reader_writer_lock`リーダーとしてオブジェクトをロックします。  
  
```
class scoped_lock_read;
```  
  
##  <a name="try_lock"></a>try_lock 

 ブロックすることがなく、ライターとしてのリーダー ライター ロックを取得しようとしています。  

## <a name="scoped_lock_read_ctor"></a>scoped_lock_read::scoped_lock_read 

構築、`scoped_lock_read`オブジェクトを取得し、`reader_writer_lock`で渡されるオブジェクト、`_Reader_writer_lock`に閲覧者としてのパラメーターです。 ライターとして別のスレッドによってロックが保持されているか、保留中のライターが、この呼び出しはブロックされます。  
  
```
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```  
  
#### <a name="parameters"></a>パラメーター  
 `_Reader_writer_lock`  
 `reader_writer_lock`に閲覧者としてを取得するオブジェクト。  
  
## <a name="a-namescopedlockreaddtor--readerwriterlockscopedlockreadscopedlockread-destructor"></a><a name="scoped_lock_read_dtor">reader_writer_lock::scoped_lock_read:: ~ scoped_lock_read デストラクター
破棄、`scoped_lock_read`オブジェクトし、そのコンス トラクターでロックを解放します。  

```
~scoped_lock_read();
```  
  
## <a name="try_lock"></a>try_lock 

```
bool try_lock();
```  
  
### <a name="return-value"></a>戻り値  
 ロックが取得された場合、値`true`。 そうしないと、値`false`です。  
  
##  <a name="try_lock_read"></a>try_lock_read 

 ブロックせずに閲覧者としてのリーダー ライター ロックを取得しようとします。  
  
```
bool try_lock_read();
```  
  
### <a name="return-value"></a>戻り値  
 ロックが取得された場合、値`true`。 そうしないと、値`false`です。  
  
##  <a name="unlock"></a>ロックを解除します。 

 リーダーまたはライターがロックされているユーザーに基づいてのリーダー ライター ロックを解除します。  
  
```
void unlock();
```  
  
### <a name="remarks"></a>コメント  
 ロックで待機しているライターがある場合、ロックの解放が常に、FIFO 順で次の書き込みにします。 このロックはライターには偏りがあり、ライターの継続的な負荷の下での閲覧者が餓死することです。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [critical_section クラス](critical-section-class.md)

