# [KSIF-11] Use h5py 2.8.0

윈도우에서 h5py의 최신 버전인 2.9.0을 사용할 시 HDF에러가 발생한다. 이를 방지하기 위해 ksif 라이브러리에서 h5py 2.8.0 버전을 사용하도록 한다.

from ksif import Portfolio
pf = Portfolio()
Traceback (most recent call last):
  File "<input>", line 1, in <module>
  File "C:\Users\willbe\AppData\Local\Programs\Python\Python36\lib\site-packages\ksif\util\checker.py", line 20, in check_not_empty
    result = func(*args, **kwargs)
  File "C:\Users\willbe\AppData\Local\Programs\Python\Python36\lib\site-packages\ksif\core\frame.py", line 78, in __init__
    data, self.benchmarks = download_latest_data()
  File "C:\Users\willbe\AppData\Local\Programs\Python\Python36\lib\site-packages\ksif\util\memoization.py", line 18, in memoized_func
    cache[key] = func(*args, **kwargs)
  File "C:\Users\willbe\AppData\Local\Programs\Python\Python36\lib\site-packages\ksif\util\retrial.py", line 31, in f_retry
    return func(*args, **kwargs)
  File "C:\Users\willbe\AppData\Local\Programs\Python\Python36\lib\site-packages\ksif\io\downloader.py", line 44, in download_latest_data
    latest_company_data = _download_data(latest_company_file_name, latest_company_id)
  File "C:\Users\willbe\AppData\Local\Programs\Python\Python36\lib\site-packages\ksif\io\downloader.py", line 53, in _download_data
    latest_company_data = custom_read_hdf(local_company_file_path)
  File "C:\Users\willbe\AppData\Local\Programs\Python\Python36\lib\site-packages\ksif\io\downloader.py", line 63, in custom_read_hdf
    latest_korea_data = read_hdf(path, key=TABLE, format=TABLE)
  File "C:\Users\willbe\PycharmProjects\FML\venv\lib\site-packages\pandas\io\pytables.py", line 368, in read_hdf
    store = HDFStore(path_or_buf, mode=mode, **kwargs)
  File "C:\Users\willbe\PycharmProjects\FML\venv\lib\site-packages\pandas\io\pytables.py", line 463, in __init__
    raise ValueError('format is not a defined argument for HDFStore')
ValueError: format is not a defined argument for HDFStore
