# breed-name-extractor
uses a simple regex to extract the breed names from he oxford --IIIT Pet dataset
def breed_extrt(directory):
    breed_names = [] # Initialize an empty list to store breed names
    for i in directory.ls():
      image_name = i.name
      #print(L(i)) # You can uncomment this if you want to see the path being processed
      rev_image_name = image_name[::-1]
      remv_unwtd = re.findall(r'[^jpg.\d]', rev_image_name)
      remv_unwtd.reverse()
      remv_unwtd = ''.join(remv_unwtd)
      breed_name=remv_unwtd.removesuffix('_')# remove the last undersore
      breed_names.append(breed_name) # Add the extracted breed name to the list
    return breed_names # Return the list of breed names after the loop finishes




