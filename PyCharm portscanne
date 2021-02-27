import socket
from IPy import IP

def scan(target,):
    converted_ip = check_ip(target)
    print('\n' + '[+] 0 scanning target] ' + str(target))
    for port in range(1,500):
        scan_port(converted_ip, port)

def check_ip(ip):
    try:
        IP(ip)
        return (ip)
    except ValueError:
        return socket.gethostbyname(ip)


def get_banner(s):
    return s.recv(1024)

def scan_port(ipaddress, port):
    try:
        sock = socket.socket()
        sock.settimeout(0.05)
        sock.connect((ipaddress, port))
        try:
            banner = get_banner(sock)
            print('[+] open port '+ str(port)+ ' : ' + str(banner.decode().strip('\n')))
        except:
            print('[+] open port ' + str(port))


    except:
        pass


if __name__ == "__main__":
    targets = input('[-] Enter Target/s To Scan(split multiple targets with (,): ')
    if ',' in targets:
        for ip_add in targets.split(','):
            scan(ip_add.strip(' '))
    else:
        scan(targets)

