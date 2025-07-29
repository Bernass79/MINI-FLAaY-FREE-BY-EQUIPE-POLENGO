local rekeste = http and http.request or syn and syn.request or request

hookfunction(rekeste, function(args)
    if args.Url:find("scriptsbinsauth.vercel.app/api/verify%-key") then
    

        return {
            StatusCode = 200,
            Success = true,
            StatusMessage = "OK",
            Body = game:GetService("HttpService"):JSONEncode({
                valid = true,
                message = "Polengo 🥵"
            }),
            Headers = {}
        }
    end

    return rekeste(args)
end)


task.wait(1)

 loadstring(game:HttpGet('https://raw.githubusercontent.com/Bernass79/rtt/refs/heads/main/README.md'))()
