forkまたはcloneしたリポジトリを本家リポジトリに追従させる手順
----------
// リモートリポジトリとして、オリジナルのリポジトリを upstream という名前で設定します。
git remote add upstream （追従先URL）

// upstreamブランチにfetchする
git fetch upstream

// masterブランチにマージする
git merge upstream/master
