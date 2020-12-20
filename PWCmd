# pyhton_Web_Crawaler
#Contains Web Crawler 

import requests
from bs4 import BeautifulSoup



def main_site(max_pages):
    page = 1


    while page <= max_pages:
        print('page=', page)
        site ="https://wall.alphacoders.com/by_sub_category.php?id=173173&name=Naruto+Wallpapers&page="
        url = site + str(page)
        source_code = requests.get(url)
        plain_text  = source_code.text
        soup = BeautifulSoup(plain_text)
        for link in soup.find_all('a',{'class':"custom-nav-tabs-element"}):
            href = link.get('href')
            title = link.string
            print(href)
            print(title)
            get_single_item_data(href)
        page+=1

def get_single_item_data(item_url):
    print("INSIDE DATA")
    source_code = requests.get(item_url)
    plain_text = source_code.text
    soup = BeautifulSoup(plain_text)
    for link in soup.find_all('a'):
        href = link.get('href')
        print(href)


main_site(2)



