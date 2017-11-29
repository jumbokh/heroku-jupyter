# Malo修改為python2.7版的memo

- 這個分支是由原master分出來的 (python3)

- 新增一個檔案"conda_runtime.txt"
  - 指出要使用的minicron的版本：Miniconda2-latest-Linux-x86_64.sh
  - 在deploy時，會到 "https://repo.continuum.io/miniconda/" 這地方抓安裝檔來裝
  - 若沒有新增檔案，會預設使用 "Miniconda3-latest-Linux-x86_64.sh" ，
  - 詳情見 <https://github.com/pl31/heroku-buildpack-conda/blob/master/bin/compile>
  
- 修改"environment.yml"  
  預先安裝pandas, matplotlib, pymongo, imgurpython, PyMySQL等自己需要的套件，不然每次休眠後，你就要到terminal重裝一次…  
![修改後程式截圖](https://imgur.com/We4J6gB.png)
<pre><code>
  - pip:
    - pgcontents
    - pandas
    - matplotlib
    - pymongo
    - imgurpython
    - SQLAlchemy
    - PyMySQL
    - git+git://github.com/ipython-contrib/jupyter_contrib_nbextensions.git
    - mock
</code></pre>

### *同時安裝 Python3 & 2.7 -->還沒想到怎麼搞，若有人搞定，再請通知我一下…
