# inspec_sample_profile
#Disallow insecure protocols by testing

describe package('telnetd') do
  it { should_not be_installed }
end

describe inetd_conf do
  its("telnet") { should eq nil }
end


# run test locally
inspec exec test.rb
