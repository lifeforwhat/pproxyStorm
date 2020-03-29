import os
import psutil

def get_bind_ips(except_ip_list=[] , except_ip_word_list=[] , except_keyword_list=[]):
    ips = psutil.net_if_addrs()
    result = []
    for name in ips:
        skip = False
        for blackkeyword in except_keyword_list:
            if blackkeyword in name:
                skip = True
                break
        if skip == True:continue

        for black_ip_keyword in except_ip_word_list:
            if black_ip_keyword in ips[name][1].address:
                skip = True
                break
        if skip == True:continue

        for black_ip in except_ip_list:
            if black_ip == ips[name][1].address:
                skip = True
                break
        if skip == True:continue

        result.append(ips[name][1].address)
    return result

def make_proxy_server(port, external_ip):
    cmd = "pproxy -l http://192.168.130.1:%s/@%s" % (port, external_ip)
    print(cmd)
    os.system(cmd)

if __name__ == '__main__':
    ips = get_bind_ips(except_ip_list=['192.168.130.1','192.168.164.1'] , except_ip_word_list=['169.254','127.0.0.1'] , except_keyword_list=['Loopback'])
    ips_count = len(ips)
    import multiprocessing

    # Process 생성
    process = []
    for count , ip in enumerate(ips):
        p = multiprocessing.Process(target=make_proxy_server, args=(20000 + count , ip,), daemon=True)
        process.append(p)
        p.start()
    for p in process:
        p.join()
